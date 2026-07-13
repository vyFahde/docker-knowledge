# Resumo da Aula 14

- Revisão do ciclo de vida de um contêiner, com uso dos comandos `docker create` e `docker start`.
- Comando `docker ps --all` é utilizado para verificar o status dos contêineres, mostrando que contêineres saídos podem ser reiniciados.
- Exemplo prático: criação e execução de um contêiner com `docker run BusyBox echo hi there`, que depois sai.
- Containers saídos podem ser reiniciados usando `docker start` seguido do ID do contêiner.
- Importante usar a flag `-a` com `docker start` para ver a saída do comando executado dentro do contêiner.
- Diagrama apresentado para ilustrar os comandos e processos.
- Comando padrão não pode ser alterado ao reiniciar o contêiner.
- Importância de entender o ciclo de vida dos contêineres para solucionar problemas e depurar.
[[Iniciando, finalizando e reiniciando um container]]