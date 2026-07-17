

Para gerenciar o ciclo de vida dos múltiplos contêineres do Docker Compose, usamos comandos específicos da CLI do Docker Compose.

## Comandos Principais
- `docker-compose up`: Cria e inicia todos os contêineres especificados no arquivo `docker-compose.yml` da pasta.
- `docker-compose up -d`: Inicia os contêineres em segundo plano (detached mode), liberando o terminal.
- `docker-compose down`: Para e remove os contêineres e as redes virtuais criadas pelo compose.
- `docker-compose up --build`: Força a reconstrução das imagens locais do zero antes de iniciar os contêineres (útil se você alterar arquivos como o Dockerfile ou instalar dependências no `package.json`).
- `docker-compose ps`: Mostra o status dos contêineres que estão rodando na aplicação gerenciada pelo Docker Compose atual.

## Políticas de Reinicialização (Restart Policies)
Definimos políticas de reinicialização no arquivo `docker-compose.yml` sob a chave `restart`. Elas dizem o que o Docker deve fazer se o contêiner falhar ou parar de rodar:

| Política | Ação | Exemplo de Uso |
|---|---|---|
| `no` | (Padrão) Não reinicia o contêiner sob nenhuma circunstância. | Scripts de uso único ou testes manuais. |
| `always` | Sempre tenta reiniciar o contêiner se ele parar, por qualquer motivo (crash, saída bem-sucedida, etc.). | Servidores Web críticos, Redis. |
| `on-failure` | Reinicia apenas se o contêiner sair com um código de erro (status diferente de zero). | Tarefas em lote ou background workers. |
| `unless-stopped` | Sempre reinicia o contêiner, a menos que ele tenha sido explicitamente parado pelo usuário via comando (como `docker stop` ou `docker-compose down`). | Servidores web em ambientes de desenvolvimento. |

[[Multi-container e Docker Compose]]
[[Configurando o Docker Compose]]
