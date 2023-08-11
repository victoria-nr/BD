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

[« Anterior](exercicis0.md) | [Següent »](8_triggers.md)
# <a name="main"></a>**7. Missatges i excepcions**


Al llarg dels exemples i exercicis que hem fet fins ara, ens ha vingut molt bé traure algun missatge, per veure com anava l'execució de les funcions. El que feem era provocar un aconteixement, en aquest cas una notícia, un avís. Podem utilitzar la mateixa sentència per a provocar també un error, amb el conseqüent avortament de l'execució de la funció. Anem a veure-ho amb més detall.

RAISE nivell 'format' [,variable1[,...]];

En nivell posarem un dels següents: **DEBUG**, **LOG**, **INFO**, **NOTICE**, **WARNING** o **EXCEPTION**, on la major part només donen un avís (amb l'encapçalament corresponent). Però **EXCEPTION** a més de traure l'avís avorta l'execució.

En format posarem una cadena amb el comentari que vulguem. Podrem posar **%** les vegades que vulguem, i se substituiran pel contingut de les variables que tinguem a continuació.

Així, per exemple, creem una funció de salutació:

CREATE OR REPLACE FUNCTION SALUTACIO() RETURNS VOID as $COS$

DECLARE

`    `s1 text := 'Joanet';

`    `s2 date := CURRENT\_DATE;

BEGIN

`    `RAISE NOTICE 'Hola';

`    `RAISE NOTICE 'Hola, %. Avui és %',s1,s2;

`    `RAISE NOTICE 'Què tal?';

END; $COS$

LANGUAGE 'plpgsql';

Si ara fem:

SELECT SALUTACIO();

Provocarà la següent eixida (en la pestanya **Output**):

Hola, Joanet. Avui es 2022-02-14
Què tal?

En canvi si la canviem el primer RAISE NOTICE per un **RAISE EXCEPTION**, i posem un altre RAISE NOTICE davant:

CREATE OR REPLACE FUNCTION SALUTACIO() RETURNS VOID as $COS$

DECLARE

`    `s1 text := 'Joanet';

`    `s2 date := CURRENT\_DATE;

BEGIN

`    `RAISE NOTICE 'Hola';

`    `RAISE EXCEPTION 'Hola, %. Avui és %',s1,s2;

`    `RAISE NOTICE 'Què tal?';

END;

$COS$ LANGUAGE 'plpgsql';

Només trauria el primer Hola, i després donaria un error amb el missatge que li hem posat:

![](7_missatges_i_excepcions.002.png)

I no trauria això de **Què tal?**, perquè ja s'ha avortat la funció. És a dir, hem provocat nosaltres l'error

[« Anterior](exercicis0.md) | [Següent »](8_triggers.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
