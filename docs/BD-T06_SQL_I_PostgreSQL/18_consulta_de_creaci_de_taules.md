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

[« Anterior](exercicis7.md) | [Següent »](exercicis8.md)
# <a name="main"></a>**18. Consulta de creació de taules**


A banda de poder consultar informació de una o més d'una taula, la sentència SELECT pot servir per a crear una nova taula, amb estructura i dades (les que venen de la pròpia sentència SELECT). Això sí, no podrem definir d'aquesta manera ni clau principal, ni claus externes, ni cap altra restricció de les conegudes.

A més, aquesta característica escapa del estàndard ANSI SQL, per la qual cosa no li donarem excessiva importància.

Sintaxi

SELECT <columnes> INTO nova\_taula 

FROM <taules>

La sentència pot dur qualsevol clàusula o predicat dels vistos fins ara, i el resultat que done aquesta sentència, es guardarà en una nova taula, amb el nom especificat.

El nom dels camps de la nova taula seran els especificats en l'apartat <columnes>. Per tant és especialment recomanable la utilització d'àlies, ja que si en posem seran el noms dels camps de la nova taula.

Els tipus de dades dels camps seran els heretats de la consulta SELECT.

En cas d'existir ja una taula amb el nom especificat ens avisarà d'aquest fet, donant-nos la possibilitat d'esborrar la taula anterior i crear la nova o cancelar.



**Nota**

És molt recomanable, com d'altres sentències de manipulació de dades que veurem més endavant, executar primer la sentència sense el **INTO**, per a no crear la taula encara. Quan estiguem segurs que el resultat és el que desitgem, afegim el INTO, i la taula es crearà a més garanties.

Exemples

1. Crear una còpia de la taula comarques anomenada **COMARQUES\_COPIA**.

SELECT \* INTO COMARQUES\_COPIA
FROM COMARQUES

Per a no "embrutar" la Base de Dades, podem esborrar-la després d'haver vist la seua creació amb la sentència

DROP TABLE COMARQUES\_COPIA

2. Crear una taula anomenada **RESUM\_COMARQUES** que continga el nom de la comarca, el número de pobles, el total de població i l'altura mitjana

SELECT nom\_c, COUNT(\*) AS num\_pobles, SUM(poblacio) AS poblacio , SUM(extensio) AS extensio , AVG(altura) AS altura\_mitjana INTO RESUM\_COMARQUES
FROM POBLACIONS
GROUP BY nom\_c

Igual que en l'anterior, després d'haver vist la seua creació i contingut, podem esborrar-la amb la sentència

DROP TABLE RESUM\_COMARQUES

[« Anterior](exercicis7.md) | [Següent »](exercicis8.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
