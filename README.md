# Desafio 02. Iniciando aplicação

Crie uma aplicação do zero utilizando Express.

Nessa aplicação configure as seguintes ferramentas:

- Sucrase + Nodemon;
- ESLint + Prettier + EditorConfig;
- Sequelize (Utilize PostgresSQL ou MySQL);

Durante esse desafio você dará início a um novo projeto no Bootcamp, esse projeto será desenvolvido aos poucos até o fim da sua jornada onde você terá uma aplicação completa envolvendo back-end, front-end e mobile.

Esse projeto também será utilizado para a certificação do bootcamp, então bora pro código!

## Aplicação

A aplicação que iremos dar início ao desenvolvimento a partir de agora é um app agregador de eventos para desenvolvedores chamado Meetapp (um acrônimo à Meetup + App).

Nesse primeiro desafio vamos criar algumas funcionalidades básicas que aprendemos ao longo das aulas até aqui.

## Funcionalidades

Abaixo estão descritas as funcionalidades que você deve adicionar em sua aplicação.

### Autenticação

Permita que um usuário se autentique em sua aplicação utilizando e-mail e senha.

- A autenticação deve ser feita utilizando JWT.
- Realize a validação dos dados de entrada;

### Cadastro e atualização de usuários

Permita que novos usuários se cadastrem em sua aplicação utilizando nome, e-mail e senha.

Para atualizar a senha, o usuário deve também enviar um campo de confirmação com a mesma senha.

- Criptografe a senha do usuário para segurança.
- Realize a validação dos dados de entrada;

## Entrega

Esse desafio **não precisa ser entregue** e não receberá correção, mas você pode ver o resultado do código do desafio aqui: https://github.com/Rocketseat/bootcamp-gostack-desafio-02

Após concluir o desafio, adicionar esse código ao seu Github é uma boa forma de demonstrar seus conhecimentos para oportunidades futuras.

“Não espere para plantar, apenas tenha paciência para colher”!

## Comentários
Para este desafio foi escolhido o banco de dados MySQL. Abaixo seguem algumas instruções para instalação e configuração do container e do MySQL:

- Docker Hub
https://hub.docker.com/_/mysql

- Instalação
docker run --name mysql -e MYSQL_ROOT_PASSWORD=docker -p  3306:3306 -d mysql

- Pós instalação
Acessar o console do MySQL:
docker exec -it mysql bash
mysql -u root -p

- Criar um novo usuário:
CREATE USER 'meetapp'@'172%'
IDENTIFIED BY 'docker';

- Atribuir permissões ao novo usuário:
GRANT ALL
ON *.*
TO 'meetapp'@'172%'
WITH GRANT OPTION;

- Alteração necessária para logar no DBeaver:
ALTER USER 'meetapp'@'172%' IDENTIFIED WITH mysql_native_password BY 'docker';

- Outros comandos apenas para consulta:
SHOW GRANTS FOR 'meetapp'@'172%';

REVOKE ALL
ON *.*
FROM 'meetapp'@'172%';

DROP USER 'meetapp'@'172%';

- DBeaver - Configuração adicional
allowPublicKeyRetrieval: true
connectTimeout: 20000
useSSL: false
