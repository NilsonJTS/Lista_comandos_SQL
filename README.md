# Lista_comandos_SQL
Lista de comandos que eu selecionei das aulas DB IFSP e dos livros

-- Criação do bando de dados 'create'
create database DB_Vendas;

-- Seleção do banco de dados: É necessário para indicar qual base de dados deve ser usada para criar a tabela 
use DB_Vendas;

-- Criação da tabela Pessoas
create table Pessoas(
	Id_Pessoas int auto_increment primary key,   #auto incremento com chave primária
	Nome Varchar(100) not null,     #note null é para a célula exigir preenchimento
	Telefone Varchar (100),   
	Endereco Varchar (100),
	Email Varchar (100)
);


- Criação da tabela clientes
create table Cliente(
	Id_Cliente int auto_increment primary key,
	Sub_Pessoas Int,
	foreign key (Sub_Pessoas) references Pessoas(Id_Pessoas)    #Chave extrangeira colocada na celula criada na
                                                              #linha anterior, e depois a referencia que é a tabela
                                                              #e depois a celula entre () que está naquela tabela referida. 
);

-- Criação tabela Produtos
create table Produtos(
	ID_Produto int auto_increment primary key,
	Nome_Produto varchar(100) not null,
	Descricao_Produto text,
	Preco decimal(10, 2) not null,          #a função decimal( , ) recebe dois argumentos, que mostra a qt 
                                          #de caract que aceita antes da virgula e depois da vergula   
	Qt_estoque int
);

-- inserindo dados
insert into Pessoas (Nome, Telefone, Endereco, Email) values
('Nilson José', '17 98195-2248', 'Rua dos Brutos', 'nilson@gmail.com' ),
('Luiz Miguel', '17 55555-5555', 'Rua dos Tordos', 'luiz@gmail.com' ),
('Erick', '17 66666-6666', 'Rua dos Bambus', 'erick@gmail.com' ),
('Sidnei', '17 88888-8888', 'Rua das Garças', 'sidnei@gmail.com' ),
('Amanda', '17 33333-3333', 'Rua dos Uirapurus', 'amanda@gmail.com' );


insert into Cliente (Sub_Pessoas) values
(1);

insert into Pessoas (Nome, Telefone, Endereco, Email) values
('Maria Zinha', '17 12345-6789', 'Rua das Paineiras', 'mariazica@gmail.com' );

insert into Cliente (Sub_Pessoas) values
(5);

insert into Supervisor (Id_Supervisor) values
(3);

insert into Supervisor (Sub_Pessoas) values
(2);

insert into Funcionario (Sub_Pessoas) values
(4);
