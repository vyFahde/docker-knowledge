# O que é uma Imagem

Uma **imagem** de container é um **snapshot** do sistema de arquivo que contém tudo o que é necessário para executar um container. Ela inclui:
- Sistema de arquivos, com o código, bibliotecas e dependências necessárias.
- Um comando principal que será executado ao rodar o container.
- Configurações e metadados que definem o ambiente do container.

A imagem é uma **entidade estática** que, quando iniciada, gera um container em execução, isolado e consistente em qualquer ambiente onde seja utilizado.
[[Criação de imagens]]