# curso-microservices-with-node-react
Repositorio para o curso https://www.udemy.com/course/microservices-with-node-js-and-react/learn/lecture/19098958#overview

Listar as imagens
> docker image ls

Criar e Executar um container
> docker run <nome da imagem>

Podemos executar comandos alternativos dentro do container
> docker run <nome da image> <comandos>

Exemplo: docker run busybox echo hi there
O comando echo irá dar display em hi there

Listar todos os containers que estão executando
>docker ps

Listar todos os containers mesmo que não estejam sendo executados
> docker ps --all

Executar um container
>docker start <id>

Executar um container e ver o output
> docker start -a <id>

Diferenças entre "docker run" e "docker start"
- Docker run cria e executa o container e apresenta a saída
- Docker start executa porém não apresenta a saída. Apenas se
- for passado o parâmetro "-a"

Em relação ao docker start e o comando default,aquele que é passado ao iniciar o container e que será executado, este não pode se mais substituido qualquer no "docker start" no mesmo id o mesmo comando será executado.

Deletar todos os containers
> docker system prune

Obter tudo que foi emitido como saída pela execução do container (log)
> docker logs <id>

Parar a execução de um container de forma que o container possa seguir o processo padrão de parada dele. ( o tempo dado para o docker é 10s depois ele executa um docker kill)
> docker stop <id>

Parar a execução de um container imediatamente
> docker kill <id>

Executar um segundo comando dentro do container que está executando. Sem o "it" não seria possível obter o console para interagir
> docker exec -it <id> <comando>

"-it" = -i -t 
-i connect o terminal ao stdin da vm linux do container
-t conecta o terminal ao stdout e o stderr da vm do container

Obter acesso ao shell do container
> docker exec -it <id> sh      // para shell
> docker exec -it <id> bash    // para bash

Podemos executar docker run -it <image name> sh para já obter acesso ao container

Criar uma imagem
> docker build .
> docker build <docker_id>/<nome por exemplo redis>:<version>

A versão pode ser "latest"

É possível criar uma imagem a partir de uma container que está sendo executado, por exemplo, instalar manualmente cada software e depois gerar a imagem
Por exemplo:
> docker run -it alpine sh
Instalar o que for necessário após isso em uma outra janela shell executar:
> docker commit -c 'CMD ["redis-server"]' <id do container>

Docker run com mapeamento de portas
>docker run -p <porta do request>:<porta dentro do container> <image name ou id>

