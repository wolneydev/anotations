1\. Criando um servidor Nginx com bind de volume Usando a opção \--mount
Para criar um servidor Nginx com um bind de volume, execute o seguinte
comando: docker run -d \--name imagem-nginx -p 8075:80 \--mount
type=bind,source=\"\$(pwd)\"/html,target=/usr/share/nginx/html nginx

Usando a opção -v Uma outra abordagem para criar o servidor Nginx com
bind de volume é utilizando a opção -v: docker run -d \--name serverngin
-p 8098:80 -v \~/projetos/volume-ubuntu:/usr/share/nginx/html nginx

Uma vantagem de usar -v é que você pode criar pastas em tempo de
execução no container, caso o caminho local não exista.

2\. Trabalhando com Volumes Criando e Gerenciando Volumes Para criar um
novo volume, utilize o seguinte comando: docker volume create
nome-do-volume

Liste os volumes existentes com: docker volume ls

Obtenha mais detalhes sobre um volume específico com: docker volume
inspect nome-do-volume

Utilizando Volumes em Containers Associe um volume a um container
usando: docker run -d \--name ngnixwww -v nome-do-volume:/app nginx
docker run -d \--name ngnixyyy -v nome-do-volume:/app nginx

Limpando Volumes Não Utilizados Remova volumes não utilizados com:
docker volume prune

3\. Gerenciando Containers e Imagens

Liste as imagens disponíveis com: docker images

Remova uma imagem usando: docker rmi nome-da-imagem

Remova todos os containers usando seus IDs: docker rm \$(docker ps -a
-q) -f

Exiba todos os IDs dos containers com: docker ps -a -q

4\. Trabalhando com Redes Crie uma rede do tipo bridge com: docker
network create \--driver bridge minharede

Liste as redes existentes com: docker network ls

Associe uma rede a um container usando: docker run -d -it \--name
ubuntu1 \--network minharede bash

Altere a rede padrão de um container usando: docker network connect
nome-da-rede nome-do-container

Essas anotações fornecem uma base sólida para entender o Docker e o
Nginx. A prática desses comandos aprimorará sua compreensão e
habilidades no uso eficiente de containers para o desenvolvimento e
implantação de aplicações. Lembre-se de consultar a documentação oficial
do Docker para explorar recursos mais avançados.
