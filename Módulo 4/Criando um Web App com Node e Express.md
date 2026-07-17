

Para entender como construir contêineres para aplicações reais, criamos um projeto simples usando Node.js e Express.

## Estrutura do Projeto
- `package.json`: Configuração de dependências do Node.js.
- `index.js`: Código da aplicação Express ouvindo na porta `8080`.
- `Dockerfile`: Arquivo de instruções para criar a imagem Docker da aplicação.

## Desafios Comuns na Criação da Imagem
1. **Comando não encontrado**: Ao usar imagens bases extremamente simples (como `alpine`), comandos como `npm` não estão disponíveis. Por isso, precisamos escolher uma imagem base adequada (ex: `node:14-alpine` ou `node:alpine`).
2. **Arquivos do projeto ausentes**: Por padrão, os arquivos da máquina local não estão disponíveis dentro do contêiner. Usamos a instrução `COPY` para copiar os arquivos locais para o sistema de arquivos do contêiner.

## O Dockerfile Inicial do Projeto
```Dockerfile
# Base Image com Node.js e npm pré-instalados
FROM node:14-alpine

# Diretório de trabalho para evitar sobreposição na raiz
WORKDIR /usr/app

# Instalação de dependências separada para aproveitar o cache
COPY ./package.json ./
RUN npm install 

# Cópia do restante do código fonte
COPY ./ ./

# Comando de inicialização padrão
CMD ["npm", "start"]
```

[[Mapeamento de portas e diretório de trabalho]]
[[Minimizando reinstalações com o Cache de Build]]
