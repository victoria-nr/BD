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

[« Anterior](exercicis2.md) | [Següent »](exercicis3.md)
# <a name="main"></a>**13. La clàusula GROUP BY**


Agrupa totes les files amb valors iguals d'una o d'unes columnes



Sintaxi

SELECT <columnes>
FROM <taules> 

GROUP BY <columnes>

Per cada fila amb valors iguals de les columnes de la clàusula **GROUP BY**, en trau només una, és a dir, les agrupa.

Les ***funcions d'agregat*** agafen tot el seu sentit i potència combinades amb el **GROUP BY**: tornaran un valor per cada grup. Així, per exemple, aquesta sentència traurà quantes poblacions hi ha en cada comarca:

SELECT COUNT(\*)
FROM POBLACIONS
GROUP BY nom\_c

Si volem excloure files per a que no entren en les agrupacions, ho farem per mig de la clàusula **WHERE**. En aquest exemple ens aprofitem del codi de municipi, que en el cas dels municipis de la província de Castelló és 12000 i pico.

SELECT COUNT(\*)
FROM POBLACIONS
WHERE cod\_m >= 12000 and cod\_m < 13000
GROUP BY nom\_c



Quan tenim agrupacions de files, bé perquè utilitzem la clàusula GROUP BY, bé perquè entre les columnes que es trien en el SELECT hi ha alguna funció d'agregat, o les dues coses a l'hora, es poden cometre errors amb una relativa facilitat. Quan hi ha una agrupació **totes les columnes que seleccionem amb el SELECT hauran d'estar en el GROUP BY, o bé estar dins d'una funció d'agregat**. En cas contrari ens donarà error. Per exemple, aquesta consulta funciona bé, i de fet és millor consulta que les d'abans, ja que ens diu la comarca i el numero de pobles que té cadascuna:

SELECT nom\_c, COUNT(\*)
FROM POBLACIONS
GROUP BY nom\_c

Però aquesta no:

SELECT nom\_c, COUNT(\*), cod\_m
FROM POBLACIONS
GROUP BY nom\_c

És sintàcticament incorrecta, i a banda no té sentit: si agrupem tots els pobles de la mateixa comarca ¿com hem de poder traure després el codi del municipi de cada poble?.

Com és relativament fàcil cometre aquest error, haurem d'identificar aquest error, per a poder solucionar-lo.

Per exemple, aquesta consulta ens dóna la població més alta de cada comarca:

SELECT nom\_c, MAX(altura)
FROM POBLACIONS
GROUP BY nom\_c

Però si intentàrem traure també el nom de la població més alta de cada comarca:

SELECT nom\_c, MAX(altura), nom
FROM POBLACIONS
GROUP BY nom\_c

ens donaria el següent error:

![](13_la_clusula_group_by.002.png)

Hem d'aprendre a identificar aquest error, i solucionar-lo. En aquest cas el solucionarem llevant el camp **Nom**. La sentència per a poder traure el nom de la població més alta de cada comarca és complicada, i encara no podem fer-la.

Exemples

1. Comptar el nombre d'instituts de cada població.

SELECT cod\_m, COUNT(\*)
FROM INSTITUTS
GROUP BY cod\_m



2. Comptar el nombre de comarques de cada província.

SELECT provincia, COUNT(\*)
FROM COMARQUES
GROUP BY provincia



3. Calcular l'altura màxima, mínima i l'altura mitjana de cada comarca.

SELECT nom\_c, MAX(altura), MIN(altura), AVG(altura)
FROM POBLACIONS
GROUP BY nom\_c



4. Comptar el nombre d'instituts de cada població i cada codi postal.

SELECT cod\_m, codpostal, COUNT(\*)
FROM INSTITUTS
GROUP BY cod\_m, codpostal



[« Anterior](exercicis2.md) | [Següent »](exercicis3.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
