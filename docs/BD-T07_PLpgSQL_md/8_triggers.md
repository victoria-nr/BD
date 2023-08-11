Bases de Dades

- [Tema 7: Programació en PostgreSQL](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [0. Nota inicial](0_nota_inicial.md)
- [1. Introducció](1_introducci.md)
- [2. PL/pgSQL](2_plpgsql.md)
- [3. Declaració de variables](3_declaraci_de_variables.md)
- [4. Instruccions](4_instruccions.md)
- [5. Funcions](5_funcions.md) 
  - [Exercicis](exercicis.md)
- [6. Utilització de cursors](6_utilitzaci_de_cursors.md) 
  - [Exercicis](exercicis0.md)
- [7. Missatges i excepcions](7_missatges_i_excepcions.md)
- [8. Triggers](8_triggers.md) 
  - [Exercicis](exercicis1.md)
- [9. Creació d'altres objectes basats en funcions](9_creaci_daltres_objectes_basats_en_funcions.md) 
  - [9.1 Operadors](91_operadors.md) 
    - [Exercicis](exercicis2.md)
  - [9.2 Operadors de classe](92_operadors_de_classe.md)
  - [9.3 Funcions d'agregat](93_funcions_dagregat.md) 
    - [Exercicis](exercicis3.md)
- [Exercicis de tot el tema](exercicis_de_tot_el_tema.md)

[« Anterior](7_missatges_i_excepcions.md) | [Següent »](exercicis1.md)
# <a name="main"></a>**8. Triggers**
Un **TRIGGER** o **disparador** és un procediment que se dispara quan s’acompleix una determinada condició que afecta a la Base de Dades: quan s’actualitza una o més d’una fila d’una determinada taula. En el moment de crear el trigger especificarem una funció que s'executarà quan es produesca l'event. Aquesta funció pot estar escrita en qualsevol llenguatge de programació instal·lat, i ha de tornar un valor especial: ***trigger***. Juguem per tant a dues bandes. Primer amb la funció que s'executarà, i quan aquesta estiga creada, el trigger pròpiament dit.

La sintaxi de creació del *trigger* és:

CREATE TRIGGER nom\_trig 

{BEFORE | AFTER} {INSERT | DELETE | UPDATE} [OR {INSERT | DELETE |UPDATE} ...]
ON nom\_taula
[FOR EACH {ROW | STATEMENT}]
EXECUTE PROCEDURE nom\_funció ([paràmetres]);

Lamentablement no tenim l’opció **OR REPLACE**, que ens permetria no haver d’esborrar el *trigger* en cas de voler refer-lo (cosa prou normal). Per tant, en el cas tan habitual de voler refer un *trigger*, primer l'haurem d'esborrar (**DROP TRIGGER**) i després tornar a fer-lo, **encara que si és una modificació en la funció no cal tocar el** *trigger*.

**BEFORE o AFTER** indiquen quan s’ha d’activar el *trigger*: abans de produir-se l’acció d’inserir, esborrar o modificar, o després.

**INSERT**, **DELETE** o **UPDATE** indiquen quina acció d’actualització de la taula provoca (o pot provocar) el *trigger*.

Una actualització pot afectar més d’una fila. Aleshores ens plantegem si s’ha de disparar el *trigger* per a cada actualització de cada fila, o si només una vegada (abans o després d’actualitzar). Ho podrem especificar per mig de **FOR EACH ROW** o **FOR EACH STATEMENT**. L'opció per defecte és la segona.

Suposem que volem activar un disparador sempre abans d’inserir sobre la taula **T1**, per a cada fila, per si la introducció no fóra correcta:

CREATE TRIGGER trigger1 BEFORE INSERT ON T1 FOR EACH ROW 

EXECUTE PROCEDURE ...;

I ara que volem activar un altre després d’esborrar un conjunt de files (per exemple per a actualitzar una altra taula):

CREATE TRIGGER trigger2 AFTER DELETE ON T1 FOR EACH STATEMENT 

EXECUTE PROCEDURE ...;

Anem a parlar ara de la funció que es crida quan es dispara el *trigger*. És una funció especial, escrita en qualsevol llenguatge definit, que com hem comentat abans ha de tornar obligatòriament un valor **TRIGGER**. De fet, amb la utilitat PgAdmin existeix l'objecte **TRIGGER FUNCTION** diferenciat de les funcions normals. Aquesta funció pot tenir paràmetres, i òbviament hauran de coincidir aquestos en la definició de la funció i en la definició del *trigger*.

Quan s'arriba a la funció, que nosaltres sempre la definirem en PL/pgSQL, s'han definit unes quantes variables especials. Anem a comentar-les:

- **NEW**: de tipus RECORD. Conté la fila que va a inserir-se o la nova informació, si va a actualitzar-se
- **OLD**: de tipus RECORD. Conté la fila que va a esborrar-se o la informació vella, si va a actualitzar-se.
- **TG\_NAME**: de tipus NAME. Conté el nom del trigger que s'ha disparat i ha cridat aquesta funció (podria ser que més d'un trigger apunte a una funció, però nosaltres no ho contemplarem)
- **TG\_WHEN**: de tipus TEXT. Indica quan actua el trigger, BEFORE o AFTER.
- **TG\_LEVEL**: de tipus TEXT. Indica de quina manera actua, ROW o STATEMENT.
- **TG\_OP**: de tipus TEXT. Indica quin event ha provocat el trigger: INSERT, UPDATE o DELETE
- **TG\_RELID**: de tipus OID. Conté l'identificador de la taula que ha provocat el trigger (podria ser més d'una).
- **TG\_RELNAME**: de tipus TEXT. Conté el nom de la taula que ha provocat el trigger
- **TG\_NARGS**: de tipus INTEGER. Indica el nombre de paràmetres que se li passen.
- **TG\_ARGV[ ]**: de tipus VECTOR de TEXT. Vector que conté els paràmetres.

` `Aquesta és una relació de variables prou extensiva. En la pràctica nosaltres només utilitzarem **NEW**, **OLD** i en tot cas **TG\_OP**.

Una funció de trigger ha de tornar o bé null, o bé un RECORD amb la mateixa estructura que la fila de la taula.

Si un trigger de nivell de fila (*for each row*) torna un valor nul, no s'efectuaran més operacions (si és un delete, que esborra més d'una fila, si la funció torna nul ja no s'intentaran esborrar més files). En canvi si torna una cosa distinta de nul, aleshores es procedirà a l'actualització amb aquest valor. Així, per curar en salut, podem fer que l'última línia de la funció de trigger siga **RETURN NEW;** Açò pot ser molt útil, ja que si és una inserció o actualització podríem fins i tot modificar la fila NEW per a que agafe els valors que nosaltres volem (per exemple: **NEW.sou := NEW.sou + 500** si estiguérem actualitzant el sou d'un empleat).

Els valors tornats per una funció trigger de nivell de ***statement*** són sempre ignorats, igual que un AFTER de nivell de fila (ja és massa tard per actuar), i per tant millor posar que tornen nul.



Anem a veure un exemple, per impedir que es modifique el nombre d'habitants d'una localitat en més de 50000 persones (augmentant o disminuint). Només té sentit el control quan es modifique la columna **poblacio**. No té sentit ni en inserir ni en esborrar una fila. I ens convé abans d’actualitzar, per poder impedir-ho.

CREATE FUNCTION val\_50000() RETURNS TRIGGER AS $cos$

BEGIN

`    `IF abs(NEW.poblacio - OLD.poblacio) > 50000 THEN

`        `RAISE EXCEPTION 'Massa diferència. No pot ser!!';

`    `END IF;

`    `RETURN NEW;

END; $cos$ 

LANGUAGE plpgsql;

CREATE TRIGGER tr\_val\_50000 BEFORE UPDATE ON POBLACIONS

`    `FOR EACH ROW

`    `EXECUTE PROCEDURE val\_50000();

Podríem comprovar el funcionament del trigger actualitzant alguna fila de la taula POBLACIONS:

UPDATE POBLACIONS

`    `SET poblacio = 1000

`    `WHERE nom='Castelló de la Plana';

Com veieu estem intentant actualitzar la població de Castelló de la Plana a 1.000 habitants. Com que la població actual és de 173.841, hi haurà una diferència de més de 50.000 habitants, i per tant el trigger impedirà l'actualització:

![ref1]

**Nota**

En DBeaver veurem els triggers en la taula a la qual afecten.

![ref2]



Mirem un altre exemple: un trigger que actualitza automàticament el nombre d'instituts de la taula **PROVINCIES** (teniu la sentència de creació en la pregunta 0 d'aquest tema) quan s'insereix o s'esborra un institut. Primer s'haurà de mirar la província de l'institut que s'està introduint o esborrant, i després s'incrementa o decrementa el nombre d'instituts de la província:

CREATE OR REPLACE FUNCTION act\_inst() RETURNS TRIGGER AS $cos$

DECLARE aux text;

BEGIN

`    `IF TG\_OP='INSERT'

`    `THEN

`        `SELECT provincia INTO aux FROM POBLACIONS,COMARQUES

`            `WHERE POBLACIONS.nom\_c=COMARQUES.nom\_c AND

`                `POBLACIONS.cod\_m = NEW.cod\_m;

`        `UPDATE PROVINCIES

`            `SET instituts = instituts + 1

`            `WHERE provincia = aux;

`    `ELSE

`        `SELECT provincia INTO aux FROM POBLACIONS,COMARQUES

`            `WHERE POBLACIONS.nom\_c=COMARQUES.nom\_c AND

`                `POBLACIONS.cod\_m = OLD.cod\_m;

`        `UPDATE PROVINCIES

`            `SET instituts = instituts - 1

`            `WHERE provincia = aux;

`    `END IF;

`    `RETURN NEW;

END; $cos$ 

LANGUAGE plpgsql;

CREATE TRIGGER tr\_act\_inst AFTER INSERT OR DELETE ON INSTITUTS

`    `FOR EACH ROW

`    `EXECUTE PROCEDURE act\_inst();

Podrem comprovar-ho, per exemple, introduint un nou registre. Abans de l'actualització, el contingut de la taula PROVINCIES és:

![ref3]

Inserim ara el nou institut, corresponent a Castelló (el codi del municipi és 12040)

INSERT INTO INSTITUTS VALUES

`    `('12004299','IES MARJALERIA','CAMÍ LA PLANA','S/N',12003,12040);

El contingut de la taula PROVINCIES és ara:

![ref4]

Un últim exemple per a veure el de **FOR EACH STATEMENT**. Intentarem fer un trigger per a que actualitze la població de les províncies. Ara anem a plantejar-lo de manera que calcule una altra vegada el total de les poblacions. Per tant, segurament és millor calcular-ho quantes menys vegades millor; és a dir, si es fan unes quantes actualitzacions de les poblacions, doncs calcular al final de totes elles (i no després de cadascuna).

CREATE OR REPLACE FUNCTION act\_pobl() RETURNS TRIGGER AS $cos$

BEGIN

`	`UPDATE PROVINCIES

`	`SET habitants = (SELECT SUM(poblacio)

`    					`FROM COMARQUES,POBLACIONS

`    					`WHERE COMARQUES.nom\_c=POBLACIONS.nom\_c and

`    						`provincia=PROVINCIES.provincia);

`	`RETURN NEW;

END; $cos$

LANGUAGE plpgsql;

CREATE TRIGGER tr\_act\_pobl AFTER INSERT OR DELETE OR UPDATE

`	`ON POBLACIONS FOR EACH STATEMENT

`	`EXECUTE PROCEDURE act\_pobl();

Per a poder comprovar el resultat del trigger anem a fer una operació d'actualització. Per exemple anem a incrementar cada població de la comarca de l'Alcalatén en 10.000 habitants (recordeu que ja tenim un trigger que impedeix augmentar en més de 50.000).

UPDATE POBLACIONS

`    `SET poblacio = poblacio + 10000

`    `WHERE nom\_c = 'Alcalatén';

Com que la comarca té 9 pobles, la població de la província de Castelló haurà augmentat en 90.000 habitants:

![ref5]

No oblidem executar l'operació de restar 10.000 habitants als pobles de la comarca de l'Alcalatén, i llevar l'institut de la Marjaleria, per deixar les coses com estaven (encara que només són dades de prova molt desactualitzades).

UPDATE POBLACIONS

`    `SET poblacio = poblacio - 10000

`    `WHERE nom\_c = 'Alcalatén';

DELETE FROM INSTITUTS

`    `WHERE codi = '12004299';


Per esborrar un trigger, utilitzarem la instrucció **DROP TRIGGER**:

DROP TRIGGER nom\_trigger ON nom\_taula;

La modificació d'un trigger (**ALTER TRIGGER)** només permet canviar el nom d'aquest trigger.

Pot ser molt útil en ocasions desactivar un *trigger*, de manera que no tinga efecte durant una temporada, i tornar a activar-lo més avant. Està clar que sempre podríem esborrar-lo i tornar a crear-lo quan faça falta, però serà més còmoda la desactivació. Aquesta operació es fa en l'**ALTER TABLE** de la taula a la qual implica el *trigger*.

ALTER TABLE nom\_taula [ENABLE | DISABLE] TRIGGER [nom\_trigger | ALL | USER ];

Com es pot comprovar, la sentència permet activar o desactivar un *trigger* en concret, o tots els *triggers* (caldrà tenir privilegis de superusuari, ja que açò inclouria els *triggers* implicits que fan acomplir les restriccions d'integritat, i això només ho podria fer un superusuari), o els *triggers* d'usuari, que són els que no són per implementar les claus externes.

[« Anterior](7_missatges_i_excepcions.md) | [Següent »](exercicis1.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 8_triggers.002.png
[ref2]: 8_triggers.003.png
[ref3]: 8_triggers.004.png
[ref4]: 8_triggers.005.png
[ref5]: 8_triggers.006.png
