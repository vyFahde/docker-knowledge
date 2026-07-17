

O Docker Compose utiliza um arquivo YAML chamado `docker-compose.yml` para configurar os serviços da aplicação.

## Estrutura do `docker-compose.yml` do Projeto
```yaml
version: '3' # Versão do formato do Docker Compose
services: 
  redis-server: # Nome do serviço (funciona como DNS/Host)
    image: 'redis' # Usa uma imagem pronta do Docker Hub
  node-app:
    restart: always # Política de reinicialização
    build: . # Constrói a imagem usando o Dockerfile do diretório atual
    ports:
      - "4001:8081" # Mapeia a porta 4001 do host para a 8081 do contêiner
```

## Como funciona a Comunicação entre Contêineres
- Quando o Docker Compose inicia os contêineres, ele cria uma rede virtual padrão privada e adiciona ambos os contêineres a ela.
- Dentro da rede, o nome do serviço declarado em `services` (ex: `redis-server`) se torna o hostname DNS válido para comunicação interna.
- No código `index.js` da nossa aplicação Node, conectamos ao Redis passando o hostname:
  ```javascript
  const client = redis.createClient({
      host: 'redis-server', // Corresponde ao nome do serviço no compose
      port: 6379 // Porta padrão do Redis
  });
  ```
- O Docker resolve automaticamente `'redis-server'` para o IP correto do contêiner do Redis.

## Mapeamento de Portas com Docker Compose
- No arquivo `docker-compose.yml`, mapeamos `4001:8081`. 
- Qualquer requisição feita à porta `4001` da máquina host é encaminhada para a porta `8081` do contêiner `node-app`.
- **Nota**: O Redis não tem portas expostas no host (`ports: ...` não foi declarado para `redis-server`), o que é uma excelente prática de segurança, já que o Node.js consegue se conectar a ele internamente pela rede virtual do Docker, mas fontes externas à rede não conseguem acessá-lo diretamente.

[[Multi-container e Docker Compose]]
[[Comandos e Políticas de Reinicialização do Docker Compose]]
