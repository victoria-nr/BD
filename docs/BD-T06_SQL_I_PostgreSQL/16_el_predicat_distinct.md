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

[« Anterior](exercicis5.md) | [Següent »](exercicis6.md)
# <a name="main"></a>**16. El predicat DISTINCT**


Per defecte, si no especifiquem el contrari, eixiran *totes* les files de la taula o taules que acomplesquen les condicions. Així, per exemple, si de la taula d'instituts volguérem treure únicament el codi de la població, ens eixiria per exemple 12040 (el codi de Castelló) en tantes files com instituts de Castelló tinguem (concretament 14). És el mateix resultat que si haguérem posat el predicat **ALL** davant de les columnes, ja que aquest és el predicat per defecte:

SELECT ALL cod\_m
FROM INSTITUTS

Aquest resultat no és el correcte, si volem consultes com "Poblacions on hi ha instituts". Seria millor si isquera 12040 només una vegada. Açò ho aconseguirem amb el predicat DISTINCT.

En definitiva el que farà el predicat DISTINCT serà traure les files diferents del resultat que demanem. Si només demanem un camp, traurà els valors diferents d'aquest camp. Si demanem més d'un camp, traurà els valors diferents per al conjunt dels camps (és a dir les files diferents, que en un camp poden coincidir, però no en el conjunt de tots els camps)

Sintaxi

SELECT DISTINCT <columnes > 

FROM <taules>



Així, en l'exemple anterior:

SELECT DISTINCT cod\_m
FROM INSTITUTS

Hi ha una variant del DISTINCT que suporta PostgreSQL, però que no suporten altres SGBD més senzills, com Access o LibreOffice Base. És posar el DISTINCT dins d'una funció d'agregat, com per exemple COUNT. El resultat és que comptarà (o la funció implicada: sumarà calcularà la mitjana, ...) els valors diferents del camp que vaja a continuació.

Així per exemple, si volem comptar en quantes poblacions diferents tenim instituts, la consulta és tan senzilla com aquesta:

SELECT COUNT(DISTINCT cod\_m)
FROM INSTITUTS

Exemples

1. Traure les diferents provincies.

SELECT DISTINCT provincia
FROM COMARQUES

2. Traure els distints districtes (codis postals) de Castelló (codi de municipi 12040) on hi ha instituts

SELECT DISTINCT codpostal
FROM INSTITUTS
WHERE cod\_m=12040

3. Traure les distintes comarques i llengües que es parlen en elles

SELECT DISTINCT nom\_c , llengua
FROM POBLACIONS
ORDER BY 1



[« Anterior](exercicis5.md) | [Següent »](exercicis6.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
