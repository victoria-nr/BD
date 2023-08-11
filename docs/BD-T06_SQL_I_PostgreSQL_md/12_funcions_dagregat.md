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

[« Anterior](exercicis1.md) | [Següent »](exercicis2.md)
# <a name="main"></a>**12. Funcions d'agregat**


Les **funcions d'agrega**t, o funcions de domini agregat, són aquelles que trauen un resultat a partir dels valors d'un determinat camp en un conjunt de files. Així tindrem una funció per a **sumar** els valors d'una columna, o **comptar**-los, o traure la **mitjana**, o el **màxim**, ...

Actuaran sobre un conjunt de files determinat, que en principi suposarem que és tota la taula (totes les files de la taula). En la següent pregunta, veurem que el conjunt de files sobre el qual es calcula una funció d'agregat, el podrem canviar amb la clàusula **GROUP BY**.

Sintaxi

- **COUNT (\* | <expressió> )** : compta el número de files; si es posa una columna o expressió, no es comptaran els valors nuls.
- **SUM ( <expressió> )** : torna la suma de la columna o expressió especificada. Ignora els valors nuls.
- **AVG ( <expressió> )** : calcula la mitjana aritmètica de la columna o expressió especificada. Ignora els valors nuls.
- **VAR\_SAMP ( <expressió> )** : calcula la variància d'una mostra a partir de la columna o expressió especificada.
- **STDDEV ( <expressió> )** : desviació típica d'una mostra.
- **MAX ( <expressió> )** : calcula el màxim.
- **MIN ( <expressió> )** : calcula el mínim.

Per exemple, si volem saber el nombre d'Instituts:

SELECT COUNT(\*) AS "Nombre d'Instituts" 

FROM INSTITUTS;

Nota

És interessant la utilització d'àlias, per a que no apareguen capçaleres com ***count***



Exemples

1. Comptar el nombre total de pobles.

SELECT Count(\*)
FROM POBLACIONS;



2. Comptar el nombre de poblacions de la **Plana Alta**.

SELECT Count(\*)
FROM POBLACIONS
WHERE nom\_c = 'Plana Alta';



3. Calcular la mitjana d'habitants dels pobles de la **Plana Alta** i **Plana Baixa**.

SELECT AVG(poblacio)
FROM POBLACIONS
WHERE nom\_c = 'Plana Alta' OR nom\_c = 'Plana Baixa'



4. Calcular la mitjana de densitat de les poblacions. La densitat es calcula com el número d'habitants dividit per l'extensió.

SELECT AVG(poblacio/extensio)
FROM POBLACIONS;



5. Calcular l'altura màxima i mínima de tots els pobles.

SELECT MAX(altura), MIN(altura)
FROM POBLACIONS



[« Anterior](exercicis1.md) | [Següent »](exercicis2.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
