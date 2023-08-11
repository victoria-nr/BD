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

[« Anterior](exercicis5.md) | [Següent »](exercicis6.md)
# <a name="main"></a>**3.3.3 UPDATE**


Aquesta sentència servirà per a modificar algun o alguns camps de determinades files d'una taula. 

En concret també servirà per "esborrar" el contingut d'algun camp d'alguna fila. El que farem serà posar a NULL aquest camp.  

Sintaxi 

UPDATE taula 
SET camp1=valor1 [ ,camp2=valor2 [,...] ]
[ WHERE condició]; 

Posarem per tant, després d'especificar la taula, el camp (o camps) que volem canviar seguit del nou valor. En cas de voler canviar més d'un camp, aniran separats per comes. 

Només canviaran els valors de les files que acomplesquen la condició. Si no es posa condició es modificaran totes les files. 

Farem la mateixa consideració de perillositat que en el DELETE: és convenient fer primer una sentència SELECT, i quan estiguem segurs que se seleccionen només les files que volem modificar, canviar-la per UPDATE amb la modificació dels valors. També és molt convenient fer còpies de seguretat de les taules o de tota la Base de Dades. 

Exemples

1. Esborrar totes les dates d'incorporació de la taula EMPLEAT3

UPDATE EMPLEAT3 
SET data\_incorporacio=NULL;

2. Augmentar el sou un 5% als empleats del departament 6 de la taula EMPLEAT3.

UPDATE EMPLEAT3 
SET sou = sou \* 1.05
WHERE departament=6;

3. Canviar la població a Ares i el departament al 8, a tots els empleats de Castelló de la taula EMPLEAT3

UPDATE EMPLEAT3 
SET departament=8, 

poblacio='Ares'

WHERE poblacio='Castelló';



[« Anterior](exercicis5.md) | [Següent »](exercicis6.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
