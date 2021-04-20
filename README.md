# 
Projeto para envio de e-mails com workers.
# Projeto: email-worker-compose

Esse é o projeto final desenvolvido no curso [Docker: Ferramenta essencial para Desenvolvedores](https://www.udemy.com/course/curso-docker/) da plataforma de cursos online Udemy.

## Etapas

Cada commit representa uma etapa do projeto que foi concluida. Abaixo temos a ordem das etapas:

- Iniciando a composição com o banco de dados;
- Usando volumes e scripts de banco de dados;
- Começando nossa camada de front-end;
- Aplicativo para enfileirar as mensagens;
- Configurando um proxy reverso;
- Redes, dependência e banco de dados;
- Fila e workers;
- Escalar é preciso...;
- Twelve factors;
- Sobrescrevendo localmente;

## Como Executar

1. Clone o repositório para sua máquina;
2. Abra um terminal e navegue até o repositório;
3. Execute o comando: ```docker-compose up -d --scale worker=3```
4. Abra o navegador e digite [localhost](http://localhost) ;

## Observações

- É necessário ter o [Docker](https://www.docker.com/) instalado na sua máquina.

## Comandos Por Aula

Segue a lista ordenada de comandos executados em cada aula ao final da implementação da etapa do projeto.

- **Aula 53**
	- Executar o comando: ```docker-compose up```
- **Aula 54**
	- Executar o comando: ```docker-compose ps```
	- Executar o comando: ```docker-compose down```
	- **[CORREÇÃO]** Para funcionar, é preciso adicionar no arquivo docker-compose.yml, abaixo de 'volumes' o seguinte código: ```environment: POSTGRES_HOST_AUTH_METHOD=trust```
	- Executar o comando: ```docker-compose up -d```
	- Executar o comando: ```docker-compose exec db psql -U postgres -f ./scripts/check.sql```
- **Aulas 55, 56, 57 e 59**
	- Executar o comando: ```docker-compose ps```
	- Executar o comando: ```docker-compose down```
	- Executar o comando: ```docker-compose up -d```
	- Executar o comando: ```docker-compose logs -f -t```
	- Abrir o navegador e entrar na url [localhost](http://localhost).
- **Aula 58**
	- Executar o comando: ```docker-compose ps```
	- Executar o comando: ```docker-compose down```
	- Executar o comando: ```docker-compose up -d```
	- Executar o comando: ```docker-compose logs -f -t```
	- Abrir o navegador e entrar na url [localhost](http://localhost).
	- Executar o comando: ```docker-compose exec db psql -U postgres -d email_sender -c 'select * from emails'```
- **Aula 60**
	- Executar o comando: ```docker-compose ps```
	- Executar o comando: ```docker-compose down```
	- Executar o comando: ```docker-compose up -d --scale worker=3```
	- Executar o comando: ```docker-compose logs -f -t worker```
	- Abrir o navegador e entrar na url [localhost](http://localhost).
- **Aulas 61 e 62**
	- Executar o comando: ```docker-compose ps```
	- Executar o comando: ```docker-compose down```
	- Executar o comando: ```docker-compose up -d --scale worker=3```
	- Abrir o navegador e entrar na url [localhost](http://localhost).
	- Executar o comando: ```docker-compose exec db psql -U postgres -d email_sender -c 'select * from emails'```
