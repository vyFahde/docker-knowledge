# O que é um Dockerfile?

Um Dockerfile é um arquivo que contém um conjunto de instruções que o Docker usa para construir uma imagem. Ele permite a automação do processo de configuração de ambiente para containers.

## Estrutura de um Dockerfile

1. **Base Image**: Começamos especificando uma imagem base utilizando a instrução `FROM`. No exemplo, foi utilizado `FROM Alpine` como a imagem base.
   
2. **Instalação de Dependências**: Usamos a instrução `RUN` para executar comandos durante a construção da imagem. No caso da imagem do Redis, foi utilizado `RUN apk add --update Redis` para instalar a dependência do Redis.
   
3. **Comando de Inicialização**: A instrução `CMD` define o comando que será executado quando o container iniciar. 

## Exemplos de Instruções de um Dockerfile com o Redis

```Dockerfile
# Use uma imagem base
FROM Alpine

# Instale o Redis **APK= Apache Packet Manager
RUN apk add --update Redis

# Comando para executar ao iniciar o container
CMD ["redis-server"]