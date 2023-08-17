Bases de Dades

- [Tema 6: SQL - Consulta bàsica (part I)](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. DDL i DML](2_ddl_i_dml.md)
- [3. Client DBeaver: instal·lació i confiuració](3_client_dbeaver_installaci_i_confiuraci.md)
- [4. Client DBeaver: utilització](4_client_dbeaver_utilitzaci.md)
- [5. Dades dels exemples i els exercicis](5_dades_dels_exemples_i_els_exercicis.md)
- [6. Operadors](6_operadors.md)
- [7. Funcions](7_funcions.md) 
  - [7.1 Formats de les dates](71_formats_de_les_dates.md)
  - [7.2 Formats dels números](72_formats_dels_nmeros.md)
- [8. La consulta SELECT](8_la_consulta_select.md)
- [9. Consulta bàsica](9_consulta_bsica.md) 
  - [Exercicis](exercicis.md)
- [10. Àlies en les columnes](10_lies_en_les_columnes.md) 
  - [Exercicis](exercicis0.md)
- [11. La clàusula WHERE](11_la_clusula_where.md) 
  - [Exercicis](exercicis1.md)
- [12. Funcions d'agregat](12_funcions_dagregat.md) 
  - [Exercicis](exercicis2.md)
- [13. La clàusula GROUP BY](13_la_clusula_group_by.md) 
  - [Exercicis](exercicis3.md)
- [14. La clàusula HAVING](14_la_clusula_having.md) 
  - [Exercicis](exercicis4.md)
- [15. La clàusula ORDER BY](15_la_clusula_order_by.md) 
  - [Exercicis](exercicis5.md)
- [16. El predicat DISTINCT](16_el_predicat_distinct.md) 
  - [Exercicis](exercicis6.md)
- [17. La clàusula LIMIT .. OFFSET](17_la_clusula_limit__offset.md) 
  - [Exercicis](exercicis7.md)
- [18. Consulta de creació de taules](18_consulta_de_creaci_de_taules.md) 
  - [Exercicis](exercicis8.md)
- [19. Ordre amb què s'executa una sentència SQL](19_ordre_amb_qu_sexecuta_una_sentncia_sql.md)
- [Exercicis de tot el tema, amb els resultats](exercicis_de_tot_el_tema_amb_els_resultats.md)

[« Anterior](exercicis0.md) | [Següent »](exercicis1.md)
# <a name="main"></a>**11. La clàusula WHERE**


Ens servirà per establir filtres. Només eixiran les files que satisfacen la condició del filtre.

Sintaxi

SELECT <columnes> 
FROM <taules> 
WHERE <condició> ;



La condició podrà ser una o més d'una, unides en aquest cas pels operadors lògics **AND**, **OR** i **NOT**. Cada condició serà una comparació entre expressions, on poden entrar columnes, constants, paràmetres, funcions vàlides de PostgreSQL, ... unides per operadors aritmètics. Els operadors que es poden utilitzar per a fer les comparacions són:

- **<     <=     =     >=     >           <>  (!=)**   (distint)
- **BETWEEN** *valor1* **AND** *valor2* (els valors compresos entre valor1 i valor2)
- **IN** (*llista\_de\_valors*) si el valor amb què es compara està en la llista de valors (entre parèntesis i valors separats per comes)
- També podem utilitzar **LIKE** en la condició. En els exemples 6, 7 i 8 es veu la seua utilització. L'operador LIKE s'utilitza junt amb els caràcters "**comodí**": 
  - **%** (equival a 0 o més caràcters, els que siga)
  - **\_** (1 i només un caràcter, això sí, el que siga).
- **IS [NOT]** és un operador especial per a comparar amb el valor nul (**NULL**).



Recordem per una altra banda com s'escriuen les constants:

- les constants **numèriques** van tal qual, sense cometes ni res (amb el **punt** decimal, i no coma decimal)
- les constants **alfanumèriques** (de text) van entre cometes simples
- les constants de data van entre cometes simples, i PostgreSQL ja farà la conversió
- per últim el valur nul s'escriu **NULL**



Exemples

1. Traure les comarques de la província de Castelló

SELECT \*
FROM COMARQUES
WHERE provincia = 'Castelló';



2. Traure totes les poblacions que tenen de llengua el valencià.

SELECT \*
FROM POBLACIONS
WHERE llengua = 'V';



3. Traure les poblacions de la comarca de la Plana Alta de més de 300 metres d'altura

SELECT \*
FROM POBLACIONS
WHERE nom\_c = 'Plana Alta' AND altura > 300;



4. Traure els instituts dels codis postals 12001, 12002 o 12003.

SELECT \*
FROM INSTITUTS
WHERE codpostal=12001 OR codpostal=12002 OR codpostal=12003;



SELECT \*
FROM INSTITUTS
WHERE codpostal >= 12001 AND codpostal <= 12003;



SELECT \*
FROM INSTITUTS
WHERE codpostal BETWEEN 12001 AND 12003;



SELECT \*
FROM INSTITUTS
WHERE codpostal IN (12001,12002,12003);



5. Traure els pobles de la comarca **Plana d'Utiel**. Tenim la dificultat de la cometa simple, que ens serveix sempre per a delimitar una constant alfanumèrica. La manera de solucionar-ho és posar-la dues vegades

SELECT \*
FROM POBLACIONS
WHERE nom\_c = 'Plana d''Utiel';

6. Traure nom i província dels pobles que comencen per **G** (el primer cognom).

SELECT nom, nom\_c
FROM POBLACIONS
WHERE nom LIKE 'G%';



7. Traure les poblacions que estan a 40º 1' (i els segons que siguen) de latitud nord

SELECT \*
FROM POBLACIONS
WHERE latitud LIKE '40º01\_\_\_\_N';

Hem posat els 40º i 1 minut. A continuació hem posat exactament 4 caràcters, els que siga. Hem posat 4, que serien la cometa que assenyala els minuts, les 2 xifres dels segons i la doble cometa que assenyala els segons. Observeu com la cometa simple és problemàtica, ja que és la que serveix per a delimitar la constant alfanumèrica. Si volem posar-la, en la constant l'haurem de doblar (l'haurem de posar 2 vegades seguides)

SELECT \*
FROM POBLACIONS
WHERE latitud LIKE '40º01''\_\_"N';

8. Traure totes les poblacions, el nom de les quals només consta d'una paraula (no tindran espais en blanc).

SELECT \*
FROM POBLACIONS
WHERE nom NOT LIKE '% %';



9. Traure els instituts que no tenen introduït el numero del carrer.

SELECT \*
FROM INSTITUTS
WHERE numero IS NULL;

[« Anterior](exercicis0.md) | [Següent »](exercicis1.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
