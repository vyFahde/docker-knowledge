

Na maioria das aplicações modernas de produção, não temos apenas um contêiner rodando tudo. Temos múltiplos contêineres especializados que precisam cooperar (ex: servidor web, banco de dados, serviço de cache).

## O Caso de Uso: Node.js e Redis
- Desenvolvemos uma aplicação que conta o número de acessos à nossa página.
- O Node.js atua como servidor web (`node-app`).
- O Redis armazena o contador de visitas em memória (`redis-server`).

## O Desafio da Rede Isolada
- Se iniciarmos o Redis (`docker run redis`) e o Node.js (`docker run node-app`) de forma independente, o Node.js não conseguirá acessar o Redis usando `localhost`.
- O contêiner de Node tem sua própria interface de rede isolada da do Redis. Tentar conectar ao Redis via `localhost` fará com que o Node tente buscar o Redis dentro do seu próprio contêiner, onde o Redis não está rodando.
- **Solução tradicional**: Criar redes do Docker manualmente com `docker network create`. No entanto, isso é complexo e difícil de manter.

## A Solução: Docker Compose
- **Docker Compose** é uma ferramenta CLI (inclusa no Docker Desktop/Engine) que permite definir e rodar aplicações multi-contêiner.
- Com um único arquivo de configuração (`docker-compose.yml`), podemos:
  - Definir e iniciar todos os serviços de uma vez.
  - Conectar todos os contêineres na mesma rede virtualizada automaticamente.
  - Resolver problemas de DNS internos, permitindo que os contêineres conversem usando seus nomes de serviços em vez de endereços IP.

[[Configurando o Docker Compose]]
[[Comandos e Políticas de Reinicialização do Docker Compose]]
