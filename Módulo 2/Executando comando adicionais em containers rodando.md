## **docker exec -it <container id> <command>
- Ao utilizar esse comando para executar o redis-cli dentro de um container com a imagem do Redis, o terminal retornará a cli para fazer inputs de texto

- a flag -it é a junção das flags -i e -t, o -i significa que o terminal vai ser o canal de input (stdin) do comando e a flag -t é o que faz a identação e a formatação para que fique mais comprensível
- Além disso também tem a flag sh após o comando, ex: docker exec -it <container id> <sh> que dá acesso ao shell da aplicação, onde é possível executar comandos comuns de sistemas baseados em Unix 
- 