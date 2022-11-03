# docker

## Comandos:

- __docker run__ -> executar um determinado container
- __docker ps__ -> lista de containers ativos
- __docker ps -a__ -> lista de containers ativos e inativos
- __docker run ubuntu echo "Ola Mundo"__ -> exemplo de execução dentro do ubunto
- __docker run -it ubuntu__ -> Executar dentro do terminal do container ubuntu criado
- __docker start + (id container)__ -> Serve para iniciar o container pelo ID
- __docker stop + (id container)__ -> Serve para parar o container pelo ID
- __docker start -a -i + (id container)__ -> Serve para iniciar o contaner e entrar no terminal do sistema interno (Ubuntu)
- __docker rm + (id container)__ -> Exclui o container de acordoc om o ID passado
- __docker container prune__ -> Exclui todos os containers inativos
- __docker run dockersamples/static-site__ -> Exemplo de criação de um site estático
- __docker run -d dockersamples/static-site__ -> Utilizando o -d para não travar a criação de um site estático
- __docker run -d -P dockersamples/static-site__ -> Utilizando o -P(Maiúsculo) para colocar uma porta aleatória que será acessada do browser externo
- __docker port + (id container)__ -> Exibir a porta que está sendo utilizado naquele container
- __docker run -d -P --name meu-site dockersamples/static-site__ -> Escolher um nome para o site estático
- __docker run -d -p 12345:80 dockersamples/static-site__ -> Utilizando o -p(Minúsculo) para indicar uma porta do site que será acessada externamente
- __docker stop -t 0 $(docker ps -q)__ -> Parando todos os containers sem espera de tempo
- __docker run -v "/var/www" ubuntu__ -> Executando um container apontando para um volume
- __docker inspect + (id container)__ -> Inspecionando um container pelo seu ID
- __docker run -it -v "C:\Users\Alura\Desktop:/var/www" ubuntu__ -> Cria um volume apontando para uma pasta de um diretório específico na máquina
- __docker run -p 8080:3000 -v "C:\Users\Alura\Desktop\volume-exemplo:/var/www" -w "/var/www" node npm start__ -> Cria um volume apontando para uma pasta de um diretório específico na máquina, para uma porta específica e dando start em um server node

## Início dos comandos para gerar uma imagem
- __Dockerfile ou .Dockerfile__ -> Escrever tudo abaixo dentro de um arquivo desse tipo
- __FROM node:latest__ -> Dizendo que a aplicação rodará a última versão do note
- __MAINTAINER Douglas Quintanilha__ -> Exibindo o nome de quem criou
- __ENV PORT=3000__ -> Uma variável de ambiente para exibir a porta 
- __COPY . /var/www__ -> Copiando so arquivos do diretório onde está o projeto
- __WORKDIR /var/www__ -> Apontando de onde será utilizado a imagem 
- __RUN npm install__ -> Instalando as dependências do node para que a imgem funcione corretamente
- __ENTRYPOINT npm start__ -> Dando start no servico node
- __EXPOSE $PORT__ -> Setando a porta com a variável de ambiente
## Fim

- __alura@alura-estudio-03:~/Desktop/volume-exemplo$ docker build -f Dockerfile -t douglasq/node__ -> Dando build no projeto para cirar a imagem
- __docker run -d -p 8080:3000 douglasq/node__ -> Utilzando a imagem

## Publicando no servidor do docker a imagem
- __docker login__ -> Criar uma conta no docker, após isso, utilizar esse comando para logar na mesma
- __docker push douglasq/node__ -> Subir a sua imagem para que outros possam utilizar
## FIm

## Criando uma rede para os containers se conectarem entre si
- __docker network create --driver bridge minha-rede__ -> Criando uma rede própria para comunicação dos containers
- __docker run -it --name meu-container-de-ubuntu --network minha-rede ubuntu__ -> Criando um container dentro da rede criada
## Fim



## Comandos básicos link

- https://imasters.com.br/desenvolvimento/comandos-basicos-docker