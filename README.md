create database copa;
use copa;

create table tb_times(
	codigoTime int primary key auto_increment,
    nomeTime varchar(50),
    paisTime varchar(50)
);

create table tb_jogadores(
	codigoJogador int primary key auto_increment,
    nomeJogador varchar(50)
);

-- timexjogador

create table tb_timejogador(
	codigoTime_Timejogador int  not null,
    codigoJogador_Timejogador int  not null,
    foreign key (codigoTime_Timejogador) references tb_times(codigoTime),
    foreign key (codigoJogador_Timejogador) references tb_jogadores(codigoJogador)
);

create table tb_estadios(
	codigoEstadio int primary key auto_increment,
    nomeEstadio varchar(50),
    enderecoEstadio varchar(50)
);

-- tabela de jogos ?????

create table tb_jogos(
	dataHoraJogo Datetime,
    codigoTime_Jogos int not null,
    codigoEstadio_Jogos int not null,
    mandoDoJogo int,
    tipoDePartida int,
    placar int,
    foreign key (codigoTime_Jogos) references tb_times(codigoTime),
    foreign key (codigoEstadio_Jogos) references tb_estadios(codigoEstadio)
);

drop database copa;
