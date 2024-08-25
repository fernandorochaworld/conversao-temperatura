# Projeto conversão de temperatura

### Sobre o projeto

O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

### Observações do projeto

A aplicação é exposta usando a porta 8080

# docker Commands

## Build Image

docker build -t conversor-temperatura .

## List All Images

docker image ls

## Create/Run Container

docker container run -d -p 8080:8080 --name conversor-temperatura conversor-temperatura

## Stop Container

docker container stop conversor-temperatura

## Remove Container

docker container rm conversor-temperatura

## Remove Image

docker image rm conversor-temperatura

## Remove images without reference

docker image prune -f

## List All Containers

docker ps

# Docker Registry

## Login

docker login

## Build Image with Docker Registry Name

docker build -t fernandorochaworld/temperature-converter:v0.1.0 .

## Push Image

docker push fernandorochaworld/temperature-converter:v0.1.0

## Set Tag latest

docker tag fernandorochaworld/temperature-converter:v0.1.0 fernandorochaworld/temperature-converter

## Push Tag latest

docker push fernandorochaworld/temperature-converter

## Run new Image

docker container run -p 8080:8080 -d fernandorochaworld/temperature-converter
