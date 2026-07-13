## Um container parado ainda pode ser iniciado 
- Utilizando o comando docker start + flag do container, um container com status de exited pode ser reiniciado
- Ao iniciar um container com um comando, ex: docker run busybox **teste**; **não** é mais possível alterar esse comando inicial, resultando no erro "you cannot start and attach multiple containers at once", pois o Docker identifica que 2 containers tentaram iniciar ao mesmo tempo
## Docker Stop e Kill
- docker stop > Um sinal sigterm (terminate signal) será enviado ao container para que o processo termine quando encerrar sua atividade
- docker kill > Finaliza o processo **imediatamente**, independente do processo ter terminado sua atividade, ou não
- Idealmente o container deve ser parado ao invés de matá-lo

### Bônus:
- docker system prune > **remove todos os containers parados, redes não usadas por pelo menos um container, imagens não utilizadas e caches de builds**
- Ao finalizar o comando retornará a quantidade de armazenamento liberada pela limpeza 
- docker logs + id do container > retorna os logs do container especificado
[[Executando comando adicionais em containers rodando]]