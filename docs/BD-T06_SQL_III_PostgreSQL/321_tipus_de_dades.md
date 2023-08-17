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

[« Anterior](32_ddl.md) | [Següent »](322_create_table.md)
# <a name="main"></a>**3.2.1 Tipus de dades**
En el moment de definir un camp haurem d'especificar obligatòriament de quin tipus serà. Ja es van veure els tipus bàsics d'Access en el tutorial del tema 5. Ara els veurem els tipus bàsics de **PostgreSQL**, i veurem que hi haurà molts tipus similars (com en tots els SGBD).

En el següent quadre es resumeixen els tipus de dades més importants de PostgreSQL. És un conjunt molt extens, que fins i tot pot ampliar l'usuari amb la instrucció **CREATE TYPE**, com veurem al final del tema. Són especialment interessants els tipus geomètrics (amb ***POINT***, ***BOX***,...) i el **INET** (adreça IP).

<table><tr><th> </th><th valign="top"><b>TIPUS DE DADES</b></th><th valign="top"><b>DESCRIPCIÓ</b></th><th valign="top"><b>BYTES</b></th></tr>
<tr><td rowspan="4">C<br>A<br>R<br>À<br>C<br>T<br>E<br>R</td><td valign="top"><b>CHAR</b></td><td valign="top">Un caràcter.</td><td valign="top">1 byte</td></tr>
<tr><td valign="top"><b>CHAR(n)</b></td><td valign="top">Cadena fixa de n caràcters.</td><td valign="top">(4+n) bytes</td></tr>
<tr><td valign="top"><b>VARCHAR(<i>n</i>)</b></td><td valign="top">Cadena de caràcters de llargària variable, amb un màxim de <i>n</i> caràcters. S’ha d’especificar la llargària.</td><td valign="top">(4+x) bytes</td></tr>
<tr><td valign="top"><b>TEXT</b></td><td valign="top">Igual que l'anterior, però no s'ha d'especificar la llargària màxima.</td><td valign="top">(4+x) bytes</td></tr>
<tr><td rowspan="8">N<br>U<br>M<br>È<br>R<br>I<br>C</td><td valign="top"><b>DECIMAL(<i>n,d</i>)</b></td><td valign="top">Número amb una precisió de <i>n</i> xifres, amb <i>d</i> decimals. Si no es posa <i>d</i> no hi ha decimals. La precisió màxima és de 1000 xifres.</td><td valign="top">variable</td></tr>
<tr><td valign="top"><b>NUMERIC(<i>n,d</i>)</b></td><td valign="top">Igual que l'anterior</td><td valign="top"> </td></tr>
<tr><td valign="top"><b>FLOAT4 , REAL</b></td><td valign="top">Coma flotant de simple precisió (6 xifres decimals)</td><td valign="top">4 bytes</td></tr>
<tr><td valign="top"><b>FLOAT8 , FLOAT , DOUBLE PRECISION</b></td><td valign="top">Coma flotant doble precisió (15 xifres decimals)</td><td valign="top">8 bytes</td></tr>
<tr><td valign="top"><b>INT2 , SMALLINT</b></td><td valign="top">Enter (-32.768,32767)</td><td valign="top">2 bytes</td></tr>
<tr><td valign="top"><b>INT4 , INT , INTEGER</b></td><td valign="top">Enter (-2.147.483.648, 2.147.483.647)</td><td valign="top">4 bytes</td></tr>
<tr><td valign="top"><b>INT8 , BIGINT</b></td><td valign="top">Enter amb unes 18 xifres</td><td valign="top">8 bytes</td></tr>
<tr><td valign="top"><b>SERIAL</b></td><td valign="top">Autonumèric (internament es crea una seqüència)</td><td valign="top">4 bytes</td></tr>
<tr><td rowspan="4">D<br>A<br>T<br>A</td><td valign="top"><b>DATE</b></td><td valign="top">Tipus data. Valor mínim 1-1-4713 AC. Valor màxim 31-12-5874897 DC.</td><td valign="top">4 bytes</td></tr>
<tr><td valign="top"><b>TIME</b></td><td valign="top">Tipus hora. Guarda fins a la micra de segon</td><td valign="top">8 bytes</td></tr>
<tr><td><b>TIMESTAMP</b></td><td>Tipus data-hora (combinant les característiques dels dos anteriors)</td><td>8 bytes</td></tr>
<tr><td valign="top"><b>INTERVAL</b></td><td valign="top">Un interval de temps (amb precisió d'un microsegon, però que pot arribar als 178.000.000 anys)</td><td valign="top">12 bytes</td></tr>
<tr><td> </td><td valign="top"><b>BOOL</b></td><td valign="top">Booleà, amb valors True i False</td><td valign="top">1 byte</td></tr>
<tr><td rowspan="6">G<br>E<br>O<br>M<br>È<br>T<br>R<br>I<br>C</td><td valign="top"><b>POINT</b></td><td valign="top">Un punt de l'espai bidimensional (x,y) (dos float8)</td><td valign="top">16 bytes</td></tr>
<tr><td valign="top"><b>LSEG</b></td><td valign="top">Segment de línia definit per 2 punts (x1,y1) (x2,y2)</td><td valign="top">32 bytes</td></tr>
<tr><td valign="top"><b>BOX</b></td><td valign="top">Rectangle, definit pels extrems (x1,y1) (x2,y2)</td><td valign="top">32 bytes</td></tr>
<tr><td valign="top"><b>PATH</b></td><td valign="top">Conjunt de punts que representen una figura oberta o tancada: (x1,y1), ..., (xn,yn)</td><td valign="top">16+16n bytes</td></tr>
<tr><td valign="top"><b>POLYGON</b></td><td valign="top">Conjunt de punts que representen un figura tancada (x1,y1), ..., (xn,yn) (similar al path tancat)</td><td valign="top">40+16n bytes</td></tr>
<tr><td valign="top"><b>CIRCLE</b></td><td valign="top">Cercle representat pel centre i el radi</td><td valign="top">24 bytes</td></tr>
<tr><td> </td><td valign="top"><b>INET</b></td><td valign="top">Adreça IP, de 4 números separats per punts, amb número de bits de la màscara separat per /</td><td valign="top">variable</td></tr>
</table>

També disposarem d'un tipus **enumerat**. El veurem en l'última pregunta del tema.

En la documentació de PostgreSQL trobarem tots els tipus possibles: <http://www.postgresql.org/docs/9.5/static/datatype.md>



[« Anterior](32_ddl.md) | [Següent »](322_create_table.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
