Bases de Dades

- [Tema 6: SQL - DDL i consultes d'actualització (part III)](index.md)
- [3.1 Introducció](31_introducci.md)
- [3.2 DDL](32_ddl.md) 
  - [3.2.1 Tipus de dades](321_tipus_de_dades.md)
  - [3.2.2 CREATE TABLE](322_create_table.md) 
    - [Exercicis](exercicis.md)
  - [3.2.3 Restriccions (Constraint)](323_restriccions_constraint.md) 
    - [Exercicis](exercicis0.md)
  - [3.2.4 ALTER TABLE](324_alter_table.md) 
    - [Exercicis](exercicis1.md)
  - [3.2.5 DROP TABLE](325_drop_table.md)
  - [3.2.6 Índex](326_ndex.md) 
    - [Exercicis](exercicis2.md)
  - [3.2.7 Vistes](327_vistes.md) 
    - [Exercicis](exercicis3.md)
  - [3.2.8. Creació d'altres objectes: seqüències, dominis i tipus.](328_creaci_daltres_objectes_seqncies_dominis_i_tipus.md) 
    - [3.2.8.1 Seqüències](3281_seqncies.md)
    - [3.2.8.2 Dominis](3282_dominis.md)
    - [3.2.8.3 Tipus de dades](3283_tipus_de_dades.md)
- [3.3 Consultes d'actualització](33_consultes_dactualitzaci.md) 
  - [3.3.1 INSERT](331_insert.md) 
    - [Exercicis](exercicis4.md)
  - [3.3.2 DELETE](332_delete.md) 
    - [Exercicis](exercicis5.md)
  - [3.3.3 UPDATE](333_update.md) 
    - [Exercicis](exercicis6.md)
- [Exercicis de tot el tema](exercicis_de_tot_el_tema.md)

[« Anterior](exercicis.md) | [Següent »](exercicis0.md)
# <a name="main"></a>**3.2.3 Restriccions (Constraint)**


Per mig de les restriccions podrem definir dins d'una taula restriccions d'usuari com són la definició de la clau principal, claus externes, camps no nuls i camps únics. 

Hi ha dues maneres de definir restriccions: les que afecten a un únic camp (i que es posen en la mateixa definició del camp) i les que afecten o poden afectar a més d'un camp, que s'han de definir separadament de la definició dels camps. Comencem per les primeres, per ser més senzilles d'entendre: 

Restriccions de camp únic

Són restriccions que es posen en la mateixa definició del camp i només afectaran a aquest camp: van per tant després del tipus de dades del camp i abans de la coma de separació dels camps.

La sintaxi és

[ CONSTRAINT nom ] {PRIMARY KEY | UNIQUE | NOT NULL | REFERENCES taula2 [(camp1)] | CHECK (*condició*)}

Si no posem nom a la restricció (CONSTRAINT nom) PostgreSQL li assignarà automàticament un nom. Açò pot resultar còmode en ocasions, per a no haver d'inventar-nos noms per a les restriccions, però després ens limitaria a que no podríem retocar aquestes restriccions.

Els tipus de restriccions que podem definir són:

- **PRIMARY KEY**: el camp serà clau principal.

Per exemple, d'aquesta manera definirem la taula EMPLEAT3 (com la de l'apartat anterior) amb el camp dni com a clau principal. Recordeu que l'heu d'esborrar primer (potser no l'estigueu visualitzant en pgAdmin, però sí que està creada; refresqueu constantment les taules per saber la situació actual)

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) CONSTRAINT cp\_emp3 PRIMARY KEY, 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

Nota

Podeu comprovar que si no poseu nom a la restrició, és a dir si poseu directament dni **TEXT(10) PRIMARY KEY** , i aneu al disseny de la taula (fent-li clic des de pgAdmin; recordeu que heu de refrescar per a que apareguen els nous obectes), PostgreSQL posa automàticament un nom a la restricció format pel nom de la taula seguit de **\_pkey**.

Tingueu en compte també que si la taula ja existia donarà un error. Només heu d'esborrar-la primer.

- **UNIQUE**: el camp serà únic, és a dir, no es podrà agafar dues vegades el mateix valor en aquest camp (*Indexat sense duplicats* en Access). PostgreSQL generarà automàticament un índex per a aquest camp. Veurem què és un índex en la pregunta 3.2.6.

Per exemple, d'aquesta manera definiríem la taula EMPLEAT3 amb la restricció que el camp **nom** no es pot repetir (si voleu provar la sentència feu-lo en la BD **proves**, i si ja existeix l'esborreu primer):

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR CONSTRAINT u\_nom UNIQUE, 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

- **NOT NULL**: el camp no podrà agafar un valor nul (*Requerido* en Access). Hem de ser conscients que no val la pena definir com a no nula la clau principal, ja que per definició ja ho és.

Per exemple, d'aquesta manera definirem que el camp **nom** ha de ser no nul.

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR CONSTRAINT nn\_nom NOT NULL , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

- **REFERENCES**: servirà per a definir que aquest camp és una clau externa. Haurem d'especificar obligatòriament la taula a la qual apunta, i opcionalment podem posar entre parèntesis el camp de la taula al qual apunta, encara que si no ho posem, per defecte apuntarà a la clau principal (i nosaltres sempre voldrem apuntar a la clau principal).

Per exemple, d'aquesta manera podem definir la clau externa que apunta a la taula DEPARTAMENT (i que indica que l'empleat pertany al departament). Abans de crear aquesta versió de EMPLEAT3, hem de tenir creada la taula DEPARTAMENT, sinó donarà error:

CREATE TABLE DEPARTAMENT
( num\_d INT2 CONSTRAINT cp\_dep PRIMARY KEY ,
`  `nom\_d VARCHAR(50) ,
`  `director VARCHAR(10) ,
`  `data DATE );

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 CONSTRAINT ce\_emp3\_dep REFERENCES DEPARTAMENT ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE );

Com ja es va veure en el tema 3 (Model Relacional) i en el tema 5 (Access), hi ha 3 maneres d'actuar quan s'esborra o es modifica una fila de la taula principal que té associades files en la taula relacionada per mig de la clau externa. Per exemple, què fem amb els familiars d'un empleat si esborrem l'empleat? Aquestes maneres d'actuar s'han d'especificar en el moment de definir la clau externa. La manera de posar-les en SQL i el significat són les següents:

- **NO ACTION**: no es deixarà esborrar o modificar de la taula principal si en té alguna fila relacionada. És l'opció per defecte. Així en l'exemple d'EMPLEAT3, amb una clau externa que apunta a DEPARTAMENT, si intentem esborrar o modificar el numero d'un departament que té empleats, ens donarà un missatge d'error, avisant que com té registres relacionats en una altra taula no es pot esborrar o modificar.
- **CASCADE**: s'esborraran (o modificaran) en cascada els registres relacionats de la taula on està la clau externa. S'especificarà amb **ON DELETE CASCADE** o **ON UPDATE CASCADE**. 

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 CONSTRAINT ce\_emp3\_dep REFERENCES DEPARTAMENT ON DELETE CASCADE ON UPDATE CASCADE ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

D'aquesta manera si esborrem un departament de la taula DEPARTAMENT, s'esborraran també els empleats de la taula EMPLEATS3 d'aquest departament. I si en la taula DEPARTAMENT modifiquem un número de departament, per exemple de 5 a 50, aquest valor serà el nou valor en el camp departament de la taula EMPLEAT3 per a aquells que abans teníen un 5.

- **SET NULL**: posarà a nul el camp que és clau externa dels registres que estiguen relacionats amb l'esborrat o modificat de la taula principal. Així, si férem la següent definició de la taula EMPLEAT3 

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 CONSTRAINT ce\_emp3\_dep REFERENCES DEPARTAMENT ON DELETE SET NULL ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

en el cas que esborrem el departament 5, no donaria cap error per aquesta restricció d'integritat, i posaria a nul el departament d'aquells empleats que abans eren del departament 5.

- **CHECK**: farà una comprovació per a validar els valors introduïts per a aquest camp. La condició de validació ha d'anar entre parèntesis, i ha de ser una expressió, normalment de comparació del camp en qüestió amb algun valor.

Per exemple, anem a exigir que el sou siga estrictament positiu (per tipus de dades numèric, podria agafar el valor 0 o valors negatius)

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) CONSTRAINT sou\_positiu CHECK (sou > 0), 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

Evidentment es pot posar més d'una restricció en la definició d'una taula. En aquest exemple arrepleguem totes les anteriors, és a dir, definim la taula **EMPLEAT3** amb tots els seus camps, i definint la *clau principal* (**dni**), amb el camp **nom** *únic*, amb el **sou** *estrictament positiu*, i amb el camp **departament** que serà *clau externa* que apunta a la taula DEPARTAMENT. Per complicar-lo un poc més també exigirem que el camp **nom** siga *no nul*, i així veure que es pot posar més d'una restricció en un camp.

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) CONSTRAINT cp\_emp3 PRIMARY KEY , 
`  `nom VARCHAR CONSTRAINT u\_nom UNIQUE CONSTRAINT nn\_nom NOT NULL , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) CONSTRAINT sou\_positiu CHECK (sou > 0) , 
`  `departament INT2 CONSTRAINT ce\_emp3\_dep REFERENCES DEPARTAMENT ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )

Observeu que com a qüestió d'estil s'han posat noms a les restriccions que d'alguna manera suggereixen el motiu de la restricció. Així, **cp\_emp3** vol dir *clau princpal de EMPLEAT3*, **u\_nom** vol dir que el camp *nom* és *únic*, **nn\_nom** vol dir que *nom* és *no nul*, **nn\_sou** vol dir que *sou* és *no nul*, i **ce\_emp3\_dep** vol dir *clau externa de la taula EMPLEAT3 a la taula DEPARTAMENT*. Si tenim un criteri clar per als noms de les restriccions, si després les volem desactivar temporalment o senzillament esborrar-les, ho podrem fer des de SQL.

Restriccions de camp múltiple

També s'anomenen restriccions de taula, en contraposició a les anteriors, que són restriccions de camp. Són restriccions que van dins de la definició d'una taula però fora de la definició d'un camp, i que poden afectar a un o més d'un camp. S'haurà de definir expressament a quin o quins camps afecten.

La sintaxi general, en aquesta ocasió és

[ CONSTRAINT nom ] {PRIMARY KEY | UNIQUE | FOREIGN KEY | CHECK (*condicio*)} (c11 [,c12][,...]) 
[ REFERENCES taula2 [ (c21 [,c22][,...]) ] ] 
[ ON DELETE {CASCADE | SET NULL}] [ON UPDATE {CASCADE | SET NULL}] ]

Igual que abans, si no posem nom a la restricció (CONSTRAINT nom) PostgreSQL li n'assignarà un automàticament, que serà construït de manera molt lògica.

Observeu que ara sempre especifiquem el o els camps afectats.

Els tipus de restriccions són els mateixos que en el cas anterior, però la sintaxi variarà lleugerament:

- **PRIMARY KEY**: posarem entre parèntesis el camp o camps (en aquest cas separats per comes) que seran clau principal.

Per exemple, definim una altra vegada el camp dni com a clau principal de la taula EMPLEAT3

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE , 
`  `CONSTRAINT cp\_emp3 PRIMARY KEY (dni) )

I ara un altre per a definir la clau principal de FAMILIAR. Com la clau està formada per 2 camps, estem obligats a utilitzar una restricció de camp múltiple.

CREATE TABLE FAMILIAR
( dni VARCHAR(10), 
`  `nom VARCHAR, 
`  `data\_n DATE, 
`  `parentesc VARCHAR(50), 
`  `CONSTRAINT cp\_fam2 PRIMARY KEY (dni,nom) )

Com comentàvem, si la clau principal està formada per 2 camps estarem obligats a utilitzar una restricció de camp múltiple. Un **error prou comú** seria el següent:

CREATE TABLE FAMILIAR2
( dni VARCHAR(10) PRIMARY KEY, 
`  `nom VARCHAR PRIMARY KEY, 
`  `data\_n DATE, 
`  `parentesc VARCHAR(50) )

Podeu comprovar que donarà **error**, perquè estem intentant definir 2 claus principals. La clau principal és única, això sí formada per 2 camps en aquesta ocasió.

- **UNIQUE**: ara posarem entre parèntesis el o els camps que seran únics (en el seu conjunt). PostgreSQL generarà automàticament un índex per a aquesta combinació de camps. Veurem què és un índex en la pregunta 3.2.6.

Per exemple, modifiquem la definició de EMPLEAT3 (anomenant-la EMPLEAT4) , amb un camp per als **cognoms** i un camp per al **nom**. Definirem la restricció que els camps cognoms i nom (en conjunt) no es poden repetir.

CREATE TABLE EMPLEAT4 
( dni VARCHAR(10), 
`  `cognoms VARCHAR, 
`  `nom VARCHAR, 
`  `data\_naixement DATE, 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 , 
`  `CONSTRAINT u\_nom4 UNIQUE (cognoms,nom) )

- **NOT NULL**.

No existeix aquesta opció com a restricció múltiple. Per tant s'ha de definir sempre com a restricció de camp únic.

- **FOREIGN KEY**: servirà per a definir que aquest o aquestos camps són una clau externa. És la que més varia en la seua sintaxi, ja que hem d'especificar tant el o els camps d'aquesta taula que són clau externa, com la taula a la qual apunta (i en tot cas el o els camps on s'apunta, encara que si no ho posem apuntarà a la clau principal de l'altra taula, cosa que voldrem sempre):

[CONSTRAINT nom] FOREIGN KEY (c11 [,c12][,...]) REFERENCES taula2 [(c21 [,c22][,...])] [ON DELETE {CASCADE | SET NULL}] [ON UPDATE {CASCADE | SET NULL}]

En l'exemple de la clau externa que apunta a la taula DEPARTAMENT quedarà així:

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE ,
`  `CONSTRAINT ce\_emp3\_dep FOREIGN KEY (departament) REFERENCES DEPARTAMENT )

- **CHECK**: ara la condició de validació podrà afectar a més d'un camp

Per exemple podríem exigir que la data d'incorporació siga estrictament posterior a la data de naixement

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE ,
`  `CONSTRAINT check\_dates CHECK (data\_incorporacio > data\_naixement) )

O una altra una miqueta més real, anem a agafar empleats de més de 18 anys, i per tant  anem a exigir que la data d'incorporació siga més de 18 anys posterior a la data de naixement. Per a això utilitzem la funció **AGE(f1,f2)** que calcula el temps entre la data d2 i la data d1 (que ha de ser la posterior), i d'ahí extraurem els anys amb **EXTRACT(year FROM ...)**

CREATE TABLE EMPLEAT3
( dni VARCHAR(10) ,
`  `nom VARCHAR ,
`  `data\_naixement DATE ,
`  `sou NUMERIC(6,2) ,
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' ,
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE ,
`  `CONSTRAINT check\_dates 
`    `CHECK (EXTRACT(year FROM AGE(data\_incorporacio,data\_naixement) ) >=18 ) )

Evidentment, es poden barrejar les restriccions de camp únic i les de camp múltiple. Ací en tenim un exemple on s'arrepleguen moltes (no totes) les restriccions anteriors. Hem posat de camp múltiple la dels 18 anys dels empleats, perquè no hi ha un altre remei, i també la de no repetició del camp **nom**, encara que podia ser de camp únic:

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) CONSTRAINT cp\_emp3 PRIMARY KEY , 
`  `nom VARCHAR CONSTRAINT nn\_nom NOT NULL , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) CONSTRAINT sou\_positiu CHECK (sou > 0) , 
`  `departament INT2 CONSTRAINT ce\_emp3\_dep REFERENCES DEPARTAMENT ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE ,
`  `CONSTRAINT u\_nom3 UNIQUE (nom) , 
`  `CONSTRAINT check\_dates 
`    `CHECK (EXTRACT(year FROM AGE(data\_incorporacio,data\_naixement) ) >=18 ) )

[« Anterior](exercicis.md) | [Següent »](exercicis0.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
