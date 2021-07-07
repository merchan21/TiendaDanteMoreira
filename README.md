# TiendaDanteMoreira
create table CLIENTE (
   ID_CLIENTE           CHAR(25)                 not null,
   ID_CEDULA_TECNICO    CHAR(25)                 null,
   NOMBRE_C             CHAR(25)                 null,
   APELLIDO_C           CHAR(25)                 null,
   DIRECCION_C          CHAR(25)                 null,
   TELEFONO_C           CHAR(25)                 null,
   CORREO_C             CHAR(25)                 null,
   EQUIPO_C             CHAR(25)                 null,                  
   constraint PK_CLIENTE primary key (ID_CLIENTE)
);

create unique index CLIENTE_PK on CLIENTE (
ID_CLIENTE
);

insert into CLIENTE values('00021','1313769901', 'Hector','Lino','Puerto Lopez', '0994828528','linoQ@gmail.com','Hp 455'),
						  ('00022','1313762345', 'Mariano','Lino','Manta', '0994828532','Mariano@gmail.com','Dell Inspiron'),
						  ('00023','1313776544', 'Mireya','Delgado', 'Montecristi', '0994828528','Mireya@gmail.com','Asus Roak'),
						  ('00024','1313769782', 'Lisset','Cedeño', 'Manta', '0994828528','liseet@gmail.com','Lenovo Pavilon'),
						  ('00025','1313761721', 'Vanessa','Rocafuerte', 'Rocafuerte', '0994828528','Vanessa@gmail.com','toshiva'),
						  ('00026','1313769812', 'Cleotilde','Segundo', 'Quito', '0994828528','Cleo@gmail.com','Hp Stok'),
						  ('00027','1313766521', 'Olaya','Mastarreno', 'Manta', '0994828528','Ola@gmail.com','Asus Laptop2'),
						  ('00028','1313723423', 'Diego','Anchundia', 'Manta', '0994828528','Die@gmail.com','Hp Gamin');
SELECT * from CLIENTE;



create table FACTURA (
   ID_FACTURA           CHAR(25)               not null,
   ID_CLIENTE           CHAR(25)               null,
   ID_TECNICO_T         CHAR(25)               null,
   ID_SERVTEC           CHAR(25)               null,
   COD_EQUIPO           CHAR(25)               null,
   NOMBRE_F             CHAR(25)               null,
   RUC                  CHAR(25)               null,
   DESCRIPCION_F        CHAR(100)              null,
   TELEFONO_F           CHAR(25)               null,
   ESTADO               CHAR(100)              null,
   ENCARGADO            CHAR(25)               null,
   TOTALVENTA           FLOAT8                 null,
   constraint PK_FACTURA primary key (ID_FACTURA)
);

create unique index FACTURA_PK on FACTURA (
ID_FACTURA
);

insert into FACTURA values('0000030','00021','109121','10101','001','Hector','001313769901','Computadora con fallas de encendido', '0994828528','La Laptop Tenia Problemas con el encendido, se le rremplazo el boton','Tecnico Lino',30),
						  ('0000031','00022','109122','10102','002', 'Mariano','001313762345','Computadora con cambio de teclado', '0994828532','Enciende solo tiene fallos en el teclado, se le cambio el teclado','Tecnico Diego',50),
						  ('0000032','00023','109123','10103','003', 'Mireya','001313776544', 'Mantenimiento preventivo ', '0994828528','El equipo funciona correctamente, se calentaba un mantenimiento era necesario','Tecnico Maria',60),
						  ('0000033','00024','109124','10104','004', 'Lisset','001313769782', 'Mantenimiento Correctivo', '0994828528','Problemas en el disco duro, optimizacion ','Tecnico Rosa',70),
						  ('0000034','00025','109125','10105','005', 'Vanessa','001313761721', 'Venta de equipo', '0994828528','Funciona Perfectamente, venta de equipo Nuevo','Tec Marlon',80),
						  ('0000035','00026','109126','10106','006', 'Cleotilde','001313769812', 'Venta de equipo', '0994828528','Funciona Correctamente,Venta de Equipo Nuevo','Tec Asley',90),
						  ('0000036','00027','109127','10107','007', 'Olaya','001313766521', 'Actualizacion de sistema Operativo', '0994828528','Funcionando a la perfeccion, Actualizacion de sistema Operativo','Tecnico luis',10),
						  ('0000037','00028','109128','10108','008', 'Diego','001313723423', 'Recovery de datos del usuario', '0994828528','El equipo requiere formateo, recovery de datos','Tecnico andres',20);

SELECT * from FACTURA;

create table TECNICOS (
   ID_TECNICO           CHAR(25)               not null,
   ID_CEDULA_TECNICO    CHAR(25)               null,
   NOMBRE_T               CHAR(25)               null,
   APELLIDO_T             CHAR(25)               null,
   GENERO               CHAR(25)               null,
   DIRRECCION_T           CHAR(25)               null,
   TELEFONO_T             CHAR(25)               null,
   FECH_NACIMIENTO      DATE,
   constraint PK_TECNICO primary key (ID_TECNICO)
);
DROP TABLE TECNICOS;
create unique index TECNICO_PK on TECNICOS (
ID_TECNICO
);


insert into TECNICOS values('109121','1313768380','Tec Lino','Arteaga','Masculino','Puerto Lopez', '0994834223','1990/04/20'),
						  ('109122','1313768381','Tec Diego','Moreira','Masculino','Manta', '0994834224','1993/06/22'),
						  ('109123','1313768382','Tec Maria','Quijije','Femenini', 'Manta', '0994834225','1994/05/30'),
						  ('109124','1313768383','Tec Rosa','Delgado','Femenino', 'Puerto Cayo', '0994834226','1995/01/22'),
						  ('109125','1313768384','Tec Marlon','Cedeño','Masculino', 'San Mateo', '0994834227','1996/01/16'),
						  ('109126','1313768385','Tec Luis','Giler','Masculino', 'Manta', '0994834228','1998/12/25'),
						  ('109127','1313768386','Tec Mariano','Cedeño','Masculino', '0994834229', 'Masculino','1999/01/28'),
						  ('109128','1313768387','Tec Andres','Intriago','Masculino', '0994834230', 'Masculino','1997/07/21');





create table SERVICTECNICO (
   ID_SERVTEC           CHAR(25)               not null,
   ID_TECNICO_S         CHAR(25)               null,
   ID_EQUIPO            CHAR(25)               null,
   PROBLEMA             CHAR(100)               null,
   DESCRIP_SOLUCION     CHAR(100)               null,
   MATERIALES           CHAR(100)               null,
   REPUESTOS            CHAR(100)               null,
   COSTOS               CHAR(10)               null,
   constraint PK_SERVTEC primary key (ID_SERVTEC)
);

create unique index SERVTEC_PK on SERVICTECNICO (
ID_SERVTEC
);


insert into SERVICTECNICO values('10101','109121','001','Computadora con fallas de encendido','La Laptop Tenia Problemas con el encendido, se le rremplazo el boton','Desarmadores, Clips','Boton de encendido','25'),
						  		('10102','109122','002','Computadora con cambio de teclado','Enciende solo tiene fallos en el teclado, se le cambio el teclado','Desarmadores','teclado','30'),
						 		('10103','109123','003','Mantenimiento preventivo ','El equipo funciona correctamente, se calentaba un mantenimiento era necesario','desarmadors, clips, pasta termica, brocha','Pasta Termica','25'),
						  		('10104','109124','004','Mantenimiento Correctivo','Problemas en el disco duro, optimizacion ','Herramienta de desfracmentacion','ninguno','25'),
						  		('10105','109125','005','Venta de equipo','Funciona Perfectamente, venta de equipo Nuevo','ninguno','ninguno','1225'),
						  		('10106','109126','006','Venta de equipo','Funciona Correctamente,Venta de Equipo Nuevo','ninguno','ninguni','1300'),
						  		('10107','109127','007','Actualizacion de sistema Operativo','Funcionando a la perfeccion, Actualizacion de sistema Operativo','USB, booteado','ninguno','25'),
						  		('10108','109128','008','Recovery de datos del usuario','El equipo requiere formateo, recovery de datos','disco duro, pendrive','ninguno','25');


create table EQUIPO (
   COD_EQUIPO           CHAR(25)               not null,
   CED_TECNICO          CHAR(25)               null,
   COD_PRODUCTO         CHAR(25)               null,
   MODELO_DEL_EQUIPO    CHAR(25)               null,
   SERIE_DEL_EQUIPO     CHAR(25)               null,
   OTROS                CHAR(50)               null,
   FUNCIONAMIENTO       CHAR(50)               null,
   FECH_INGRESO         DATE,
   constraint PK_EQUIPO primary key (COD_EQUIPO)
);

create unique index EQUIPO_PK on EQUIPO (
COD_EQUIPO
);

insert into EQUIPO values('001','1313768380','202021','asroot','L102312932112322','cargador','funcionamiento bueno','2021/07/04'),
						 ('002','1313768381','202022','Inspiron','L102312932112323','cargador y disco duro','funcionamiento regular','2021/07/05'),
						 ('003','1313768382','202023','Noteboot','L102312932112324','cargador','Equipo no enciende','2021/07/06'),
						 ('004','1313768383','202024','Dell','L102312932112325','Disco duro','Funcionamiento bueno','2021/07/07'),
						 ('005','1313768384','202025','Macboot','L102312932112326','Memoria ram para aumentar','Equipo sin contraseña','2021/07/08'),
						 ('006','1313768385','202026','Noteboot','L102312932112327','cargador y disco duro fuera','Equipo se apaga','2021/06/02'),
						 ('007','1313768386','202027','ASRood','L102312932112328','cargador','funcionamiento bueno','2021/06/02'),
						 ('008','1313768387','202028','Hp','L102312932112329','cargador ','funcionamiento bueno','2021/06/03');



create table PRODUCTO (
   COD_PRODUCTO         CHAR(25)               not null,
   ID_PROVEEDOR         CHAR(25)               null,
   ID_FACTURA           CHAR(25)               null,
   DESCRIPCION          CHAR(100)               null,
   PRECIO               CHAR(25)               null,
   ESTADO               CHAR(25)               null,
   constraint PK_PRODUCTO primary key (COD_PRODUCTO)
);

create unique index PRODUCTO_PK on PRODUCTO (
COD_PRODUCTO
);

insert into PRODUCTO values('202021','10212345','0000030','Computadora ASUS Nueva','1500','nuevo'),
						   ('202022','10212346','0000031','Computadora HP Nueva','1000','nuevo'),
						   ('202023','10212347','0000032','Computadora LENOVO Nueva','560','nuevo'),
						   ('202024','10212348','0000033','Computadora ASUS Nueva','640','nuevo'),
						   ('202025','10212349','0000034','Computadora DELL Nueva','400','nuevo'),
						   ('202026','10212350','0000035','Computadora TOSHIVA Nueva','2000','nuevo'),
						   ('202027','10212351','0000036','Computadora SAMSUMG Nueva','1000','nuevo'),
						   ('202028','10212352','0000037','Computadora INDURAMA Nueva','1100','nuevo');



create table PROVEEDOR (
   ID_PROVEEDOR         CHAR(25)               not null,
   NOMBRE               CHAR(25)               null,
   DIRECCION            CHAR(25)               null,
   TELEFONO             CHAR(25)               null,
   PAIS                 CHAR(25)               null,
   WEBSITE              CHAR(50)               null,
   PRODUCTO             CHAR(50)               null,
   Tot_Compras          FLOAT8                 null,
   constraint PK_PROVEEDOR primary key (ID_PROVEEDOR)
);
drop table PROVEEDOR;
create unique index PROVEEDOR_PK on PROVEEDOR (
ID_PROVEEDOR
);

insert into PROVEEDOR values('10212345','Dell S.A','Florida','0994828512','Estados Unidos','www.dell.com', 'equipos informaticos',1000),
                            ('10212346','TOSHIBA S.A','CALLE 15 AV 30','0994828512','Estados Unidos','www.toshiba.com', 'equipos informaticos',10000),
							('10212347','HP S.A','ECUADOR','0994828512','Ecuador','www.hp.com', 'equipos informaticos',5000),
							('10212348','LENOVO S.A','ESPAÑA','0994828512','Estados Unidos','www.lenovo.com', 'equipos informaticos',4000),
							('10212349','ASUS S.A','llogembert','0994828512','España','www.asus.com', 'equipos informaticos',700),
							('10212350','ONHERE S.A','CHINA','0994828512','Estados Unidos','www.onhere.com', 'equipos informaticos',5000),
							('10212351','INDURAMA S.A','ESTADOS UNIDOS','0994828512','Estados Unidos','www.indurama.com', 'equipos informaticos',6000),
							('10212352','SAMGSUM S.A','MIAMI','0994828512','Estados Unidos','www.samgsum.com', 'equipos informaticos',1023);


--CONSULTAS--
--5 proveedores a los cuales mas se le compra articulos--
select ID_PROVEEDOR, NOMBRE, PAIS, WEBSITE, PRODUCTO, Tot_Compras
from PROVEEDOR ID_PROVEEDOR ORDER BY Tot_Compras DESC LIMIT 5;

--5 vendedores con mas ventas --	

select ID_TECNICO_T, NOMBRE_F, TOTALVENTA
from FACTURA ID_FACTURA ORDER BY TOTALVENTA DESC LIMIT 5;

---5 TECNICOS CON MAS REPARACIONES--

select (NOMBRE_T, APELLIDO_T, ID_TECNICO, ENCARGADO) 
from TECNICOS
join FACTURA
on TECNICOS.ID_TECNICO=FACTURA.ID_TECNICO_T LIMIT 5;
 
--consultar que tecnicos hacen reparaciones con la solucion--

select (NOMBRE_T, Apellido_T, PROBLEMA, DESCRIP_SOLUCION, REPUESTOS) 
from TECNICOS
join SERVICTECNICO
on TECNICOS.ID_TECNICO=SERVICTECNICO.ID_TECNICO_S
