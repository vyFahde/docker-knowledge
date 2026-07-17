

O processo de compilação de imagens Docker pode se tornar muito lento se as dependências forem reinstaladas a cada pequena modificação no código fonte.

## Como funciona o Cache de Build do Docker
- O Docker executa as instruções do `Dockerfile` de cima para baixo.
- Para cada instrução, se nada mudou em relação ao build anterior, o Docker usa uma versão em cache (indicado por `---> Using cache` no terminal).
- No entanto, se uma linha for alterada (ou se um arquivo copiado mudar), aquela instrução e **todas as instruções subsequentes** perdem o cache e precisam ser executadas novamente.

## O Problema com a Abordagem Ingênua
Se escrevermos o `Dockerfile` desta forma:
```Dockerfile
FROM node:alpine
WORKDIR /app
COPY ./ ./
RUN npm install
CMD ["npm", "start"]
```
- Se alterarmos uma linha no arquivo `index.js`, o comando `COPY ./ ./` detectará a alteração de arquivos e invalidará o cache.
- Consequentemente, o comando `RUN npm install` terá seu cache invalidado e será executado novamente, fazendo o download de todos os pacotes do Node.js do zero, mesmo que nenhuma dependência no `package.json` tenha mudado.

## A Solução (Abordagem Otimizada)
Dividimos a cópia de arquivos em duas etapas:
1. Copiamos **apenas** o `package.json` para o contêiner.
2. Executamos `npm install`.
3. Copiamos o restante dos arquivos do projeto.

```Dockerfile
FROM node:alpine
WORKDIR /app

# 1. Copia o package.json
COPY package.json .

# 2. Executa a instalação (Só roda se package.json mudar)
RUN npm install

# 3. Copia o restante do código
COPY . .

CMD ["npm", "start"]
```
- Desta forma, alterações em arquivos de código (como `index.js`) invalidarão apenas o cache do passo 3 (`COPY . .`), poupando o tempo precioso da instalação de pacotes no passo 2.

[[Criando um Web App com Node e Express]]
[[Mapeamento de portas e diretório de trabalho]]
