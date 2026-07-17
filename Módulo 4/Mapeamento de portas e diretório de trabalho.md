

Ao criar contêineres para servidores web, precisamos garantir que as requisições cheguem até eles e que a estrutura de arquivos interna seja organizada.

## Diretório de Trabalho (`WORKDIR`)
- Por padrão, se copiarmos arquivos usando `COPY ./ ./` sem especificar um diretório, eles serão jogados na raiz (`/`) do contêiner.
- Isso pode causar problemas, como a sobreposição de pastas cruciais do sistema operacional (ex: `/lib`, `/etc`, `/var`).
- **Solução**: Usar a diretiva `WORKDIR` para definir em qual diretório dentro do contêiner os comandos seguintes (`RUN`, `COPY`, `CMD`) serão executados.
  ```Dockerfile
  WORKDIR /usr/app
  ```
- Quaisquer arquivos copiados depois dessa linha serão colocados em `/usr/app`. Se o diretório não existir, o Docker o criará automaticamente.

## Mapeamento de Portas (Port Mapping)
- Contêineres possuem sua própria rede isolada. Por padrão, nenhuma porta de rede interna do contêiner é exposta ao computador host.
- Mesmo que um servidor Express esteja rodando na porta `8080` dentro do contêiner, tentar acessar `http://localhost:8080` do navegador falhará.
- **Solução**: Mapeamento de portas usando a flag `-p` no comando `docker run`.
  ```bash
  docker run -p <porta-no-host>:<porta-no-container> <image-id>
  ```
- Exemplo prático:
  ```bash
  docker run -p 8080:8080 joao/node-app
  ```
- **Fluxo do tráfego**:
  `Requisição Host na porta 8080` -> `Porta 8080 do host mapeada` -> `Porta 8080 de rede interna do container` -> `Servidor Express respondendo`.

[[Criando um Web App com Node e Express]]
[[Minimizando reinstalações com o Cache de Build]]
