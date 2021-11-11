# Anotações da aula

request -> route -> middleware -> function

## Docker

**Por que usar containers?**

- Aplicações rodam de forma isolada (não interferem uma na outra);
- Usa o mesmo kernel da máquina base, tornando-se mais leve e eficiente quando comparado a VM's tradicionais;
- Portabilidade (facilidade de integração com outros sistemas);

_Container usado na aula_
`docker run --name pg -e POSTGRES_USER=root -e POSTGRES_PASSWORD=root -p 5432:5432 -d postgres`

**Comandos**
`--name pg`: Atribui o nome 'pg' para o container
`-e`: Atribuir configurações ao container
`-5432:5432`: Mapeia a porta '5432' da sua máquina para a port '5432' do VM do container
`-d`: Faz o container executar em segundo plano (detached)
`docker container rm {nome do container | container id}`: Deleta o container
`docker rmi {nome do repo | image id}`: Deleta a imagem do container

`docker exec -it pg bash`: Abre o bash no container do postgres

Execute os comandos que estão em ./src/database/schema.sql

_Dentro do postgres_
`psql -U (usuario)`: Loga no usuário passado
`\l`: Lista todas as bases de dados do postgres
`\c`: Conecta em uma base de dados (\c mycontacts)
`\dt`: Lista todas as tabelas em uma base da dados
