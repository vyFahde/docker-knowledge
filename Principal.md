# 🐳 Docker & Kubernetes - Sumário Geral

Bem-vindo ao seu cofre de estudos sobre Docker e Kubernetes baseado no curso de Stephen Grider. Este arquivo serve como um **Mapa de Conteúdo (MOC)** para facilitar a navegação rápida por todos os conceitos aprendidos.

---

## 📂 Módulos de Estudo

### 🔹 Módulo 1 - Introdução e Conceitos Básicos
* [[O que é e por quê usar o Docker]]
* [[O que é um container]]
* [[O que é uma imagem]]

### 🔹 Módulo 2 - Manipulação de Containers (CLI)
* [[Ciclo de vida de um container]]
* [[Iniciando, finalizando e reiniciando um container]]
* [[Executando comando adicionais em containers rodando]]

### 🔹 Módulo 3 - Criação de Imagens Customizadas
* [[Criando uma dockerfile]]
* [[Módulo 3/Criação de imagens|Criação de Imagens - Client/Server (Módulo 3)]]

### 🔹 Módulo 4 - Projetos de Produção Reais (Node.js/Express)
* [[Criando um Web App com Node e Express]]
* [[Mapeamento de portas e diretório de trabalho]]
* [[Minimizando reinstalações com o Cache de Build]]

### 🔹 Módulo 5 - Docker Compose (Multi-containers)
* [[Multi-container e Docker Compose]]
* [[Configurando o Docker Compose]]
* [[Comandos e Políticas de Reinicialização do Docker Compose]]

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
