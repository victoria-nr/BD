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

[« Anterior](exercicis4.md) | [Següent »](exercicis5.md)
# <a name="main"></a>**3.3.2 DELETE**


Aquesta sentència servirà per **esborrar files senceres** d'una determinada taula.

Si es volen esborrar només alguns camps d'una o unes determinades files, no s'ha d'utilitzar aquesta sentència, sinó que s'haurà d'utilitzar la sentència **UPDATE** per a posar els camps a NULL.

Sintaxi

DELETE FROM taula 
[WHERE condició]

S'esborraran les files que acomplesquen la condició. Si no es posa el WHERE s'esborraran tetes les files de la taula (però no la mateixa taula, l'estructura; és a dir, continuarà existint la taula, però buida).

Per la perillositat de la sentència, és convenient fer primer una sentència SELECT, i quan estiguem segurs que se seleccionen només les files que volem esborrar, canviar-la per DELETE. També és molt convenient fer còpies de seguretat de les taules o de tota la Base de Dades.

Exemples

1. Esborrar totes les files de **EMPLEAT2**

DELETE FROM EMPLEAT2;

2. Esborrar d'**EMPLEAT3** els empleats del departament 7

DELETE FROM EMPLEAT3
WHERE departament=7;

3. Esborrar d'**EMPLEAT3** els empleats majors de 47 anys (en realitat no s'esborrarà cap perquè no tenim introduïda la data de naixement)

DELETE FROM EMPLEAT3
WHERE EXTRACT(year FROM AGE(CURRENT\_DATE,data\_naixement) )>=47;

4. Esborrar d'EMPLEAT aquells empleats que trebalen en projectes menys de 20 hores (no es molt convenient confirmar l'eliminació dels registres ja que ens quedaríem sense dades importants)

DELETE FROM EMPLEAT
WHERE dni IN (SELECT dni
`                  `FROM TREBALLA
`                  `GROUP BY dni
`                  `HAVING SUM(hores)<20);

[« Anterior](exercicis4.md) | [Següent »](exercicis5.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
