BANCO


create database estudo;
use estudo;

create table estacionamento(
id_estacionamento integer primary key auto_increment not null,
nome varchar(150)
);

create table vagas(
id_vagas integer primary key auto_increment not null,
numero smallint,
disponibilidade boolean,
precoHora numeric,
id_estacionamento integer not null,
foreign key (id_estacionamento) references estacionamento(id_estacionamento)
);

create table carro(
id_carro integer primary key auto_increment not null,
dono varchar(150),
tempoEstacionado time,
id_vaga integer not null,
foreign key (id_vaga) references vagas(id_vagas)
);

insert into estacionamento(nome) values('Estacionamento Centro');
insert into vagas(numero, disponibilidade, precoHora, id_estacionamento) values(1, 0, 10, 1);
insert into carro(dono, tempoEstacionado, id_vaga) values('Paulo', 3, 1);
