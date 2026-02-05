create database raamatBerezevski;
use raamatBerezevski;
--Tabeli žanr loomine
create table zanr
(
	zanrID int primary key identity(1,1),
	zanrNimetus varchar(50) not null,
	kirjeldus text
);
select * from zanr;
--tabeli täitmine
insert into zanr(zanrNimetus, kirjeldus)
values ('komöödia', 'see zanr teeb naljakaks'),
('tragöödia', 'See zanr teeb kurvaks'),
('fantaasia', 'Selles zanris kirjutatakse tulnukate jne');

--tabel autor
create table autor
(
	autorID int primary key identity(1,1),
	eesnimi varchar(50),
	perenimi varchar(50) not null,
	synniaasta int check(synniaasta > 1900),
	elukoht varchar(30)
);
select * from autor;

insert into autor (eesnimi, perenimi, synniaasta)
values 
('Eno', 'Raud', 1926),
('Andrus', 'Kiviränk', 1956),
('Leelo', 'Tungal', 1947);

--tabeli uuendamine
update autor set elukoht = 'Tallinn';

--kustutamine tabelist
delete from autor where autorID = 4;

--tabel raamat
create table raamat
(
	raamatID int primary key identity(1,1),
	raamatnimetus varchar(100) unique,
	autorID int,
	foreign key (autorID) references autor(autorID),
	lk int,
	zanrID int,
	foreign key (zanrID) references zanr(zanrID)
);
select * from raamat;

--kuva tabelid
select * from autor;
select * from zanr;

insert into raamat(raamatnimetus, autorID, lk, zanrID)
values ('Oskar ja asjad', 2, 200, 2),
('Sipsik', 1, 150, 5);

delete from raamat where raamatID = 1;

create table trykikoda
(
	trykikodaID int primary key identity(1,1),
	nimetus varchar(50) unique,
	address varchar(40)
);

select * from trykikoda;

insert into trykikoda(nimetus, address)
values('K-print', 'Tallinn'),
('Uniprint', 'Tallinn'),
('raamaprint', 'Tallinn');

create table trykitudRaamat
(
	trRaamatID int primary key identity(1,1),
	trykikodaID int,
	foreign key (trykikodaID) references trykikoda(trykikodaID),
	raamatID int,
	foreign key (raamatID) references raamat(raamatID),
	kogus int
);

select * from trykitudRaamat;

insert into trykitudRaamat(trykikodaID, raamatID, kogus)
values(1, 2, 500),
(2, 5, 20),
(3, 5, 300);



select * from raamat;
