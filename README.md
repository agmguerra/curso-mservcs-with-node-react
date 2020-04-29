# curso-microservices-with-node-react
Repositorio para o curso https://www.udemy.com/course/microservices-with-node-js-and-react/learn/lecture/19098958#overview


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
