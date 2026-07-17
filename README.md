# 🐳 Docker & Kubernetes - Sumário Geral

Bem-vindo ao repositório de estudos sobre Docker e Kubernetes baseado no curso de Stephen Grider. Este repositório serve como um cofre de conhecimento pessoal para facilitar a revisão rápida de todos os conceitos aprendidos.

---

## 📂 Módulos de Estudo

### 🔹 Módulo 1 - Introdução e Conceitos Básicos
* [O que é e por quê usar o Docker](Módulo%201/O%20que%20é%20e%20por%20quê%20usar%20o%20Docker.md)
* [O que é um container](Módulo%201/O%20que%20é%20um%20container.md)
* [O que é uma imagem](Módulo%201/O%20que%20é%20uma%20imagem.md)

### 🔹 Módulo 2 - Manipulação de Containers (CLI)
* [Ciclo de vida de um container](Módulo%202/Ciclo%20de%20vida%20de%20um%20container.md)
* [Iniciando, finalizando e reiniciando um container](Módulo%202/Iniciando,%20finalizando%20e%20reiniciando%20um%20container.md)
* [Executando comando adicionais em containers rodando](Módulo%202/Executando%20comando%20adicionais%20em%20containers%20rodando.md)
* [Criação de Imagens (Módulo 2)](Módulo%202/Criação%20de%20imagens.md)

### 🔹 Módulo 3 - Criação de Imagens Customizadas
* [Criando uma dockerfile](Módulo%203/Criando%20uma%20dockerfile.md)
* [Criação de Imagens - Client/Server (Módulo 3)](Módulo%203/Criação%20de%20imagens.md)

### 🔹 Módulo 4 - Projetos de Produção Reais (Node.js/Express)
* [Criando um Web App com Node e Express](Módulo%204/Criando%20um%20Web%20App%20com%20Node%20e%20Express.md)
* [Mapeamento de portas e diretório de trabalho](Módulo%204/Mapeamento%20de%20portas%20e%20diretório%20de%20trabalho.md)
* [Minimizando reinstalações com o Cache de Build](Módulo%204/Minimizando%20reinstalações%20com%20o%20Cache%20de%20Build.md)

### 🔹 Módulo 5 - Docker Compose (Multi-containers)
* [Multi-container e Docker Compose](Módulo%205/Multi-container%20e%20Docker%20Compose.md)
* [Configurando o Docker Compose](Módulo%205/Configurando%20o%20Docker%20Compose.md)
* [Comandos e Políticas de Reinicialização do Docker Compose](Módulo%205/Comandos%20e%20Políticas%20de%20Reinicialização%20do%20Docker%20Compose.md)

---

## 🛠️ Guia Rápido de Referência (Cheat Sheet)

### Manipulação de Containers (CLI)
* `docker run <imagem>` $\rightarrow$ Cria e inicia um contêiner.
* `docker run -p <porta-host>:<porta-container> <imagem>` $\rightarrow$ Roda o contêiner mapeando portas.
* `docker start -a <container-id>` $\rightarrow$ Reinicia um contêiner parado (com output no terminal).
* `docker exec -it <container-id> <comando>` $\rightarrow$ Executa comandos interativos dentro de um contêiner ativo (ex: `sh` ou `bash`).
* `docker stop <container-id>` $\rightarrow$ Para o contêiner de forma amigável (SIGTERM).
* `docker kill <container-id>` $\rightarrow$ Para o contêiner imediatamente (SIGKILL).

### Gerenciamento de Espaço
* `docker ps` $\rightarrow$ Lista contêineres ativos.
* `docker ps --all` $\rightarrow$ Lista todos os contêineres (ativos e parados).
* `docker system prune` $\rightarrow$ Remove contêineres parados, redes não utilizadas, imagens órfãs e caches de build.

### Docker Compose
* `docker-compose up` $\rightarrow$ Cria e inicializa os serviços do compose.
* `docker-compose up -d` $\rightarrow$ Inicializa em segundo plano (detached).
* `docker-compose up --build` $\rightarrow$ Força reconstrução de imagens locais antes de rodar.
* `docker-compose down` $\rightarrow$ Para e deleta todos os serviços, redes e volumes criados.
* `docker-compose ps` $\rightarrow$ Lista o status dos contêineres do compose ativo.
