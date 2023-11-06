## Comandos de Banco de Dados 

### Criar Database
* Local para criar as tabelas do sistema
```
create database NOME_DATABASE
```
### Executar o comando
```
Ctrl + Enter
```
### Selecionar Database
```
use NOME_DATABASE;
```
<hr>

## Projeto site Ecommerce
* Tabela de usuários 
* Tabela de produtos 
* Tabela de carrinho de compras

### Criar tabela de usúarios 
```
create table usuarios(
    id int not null auto_autoincrement,
    nome varchar(120) not null,
    email varchar(120) not null,
    senha varchar(120) not null,
    primary key(id)
);
```
* Id: identificados de cada registro
* Not null: campo obrigatório, não pode ser nulo
* Auto_auutoincremente: soma +1 no último registro de Id
* Varchar(120): Campo de texto com 120 caracteres 

### Criar tabela de produtos 
```
create table produtos (
    id int not null auto_increment,
    modelo vachar(120),
    nome varchar(120) not null,
    valor float not null,
    primary key(id)
);
```
### Criar tabela de carrinho
```
create table carrinho(
    id int not null auto_increment,
    id_usuario int not null,
    id_produto int not null,
    primary key(id),
    foreign key(id_usuario) references usuarios(id),
    foreign key(id_produto) references produtos(id)
);
```
* Foreign key: Chave estrangeira que recebe a referencia de outra tabela
* References: Atributo para definir a tabela e o campo estrangeiro

### Inserir usuarios
```
insert into usuarios(nome, email, senha) values('Renato Gauncho', 'Teste@teste.com', 'secret');
```
### Inserir produto
```
insert into produtos(modelo, nomen valor) values('nike', 'camiseta', '129,90');
```
### Inserir carrinho
```
insert into carrinho(id_produto) values(43,234);
insert into carrinho(id_produto) values(43,120);
insert into carrinho(id_produto) values(43,6);
```
### Listar todas as colunas de usuarios 
```
select * from usuarios; 
```
### Listar os nomes dos usuarios
```
select nome from usuarios;
```
### Listar os nomes e email dos usuarios
```
select nome, email from usuarios;
```
### Listar usuarios pelo id
```
select * from usuarios where id = 23;
```
### Verificar produtos no carrinho pelo id do usuario
```
select p.nome 
from produtos p, carrinho c
where c.id = 23 AND p.id = c.id_produto;
```