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

[« Anterior](8_la_consulta_select.md) | [Següent »](exercicis.md)
# <a name="main"></a>**9. Consulta bàsica**
El mínim que s'ha d'indicar en una instrucció SELECT és les columnes que volem i la seua procedència, que pot ser una o més d'una taula.

Sintaxi

SELECT <columnes> 

FROM <clàusula>

Opcionalment la sentència pot acabar en **punt i coma**. En **psql** és obligatori acabar en punt i coma, ja que és la manera que té de saber que acaba la instrucció (una instrucció pot ocupar més d'una línia)

I una altra consideració important és que en PostgreSQL els noms dels objectes (taules, columnes, ...) poden constar de més d'una paraula. Si el nom només consta d'una paraula es pot posar sense més problemes, però si consta de més d'una paraula (amb espis en blanc pel mig) o té algun caràcter especial, o coincideix amb alguna paraula reservada (per exemple ***any***), haurà d'anar entre **cometes dobles**. Per a estalviar problemes, és una bona pràctica fer els noms sempre d'una paraula (si es volen posar dues, unides pel guió baix).



En **<columnes>** podrem posar (separades per **comes**):

- **noms de les columnes** que volem; si hi ha confusió entre noms de camps de distintes taules, haurem de posar **Taula.columna**.
- **\*** : indica totes les columnes.
- **Taula.\*** : indica totes les columnes de la taula.
- **Funcions** (veure pregunta 6)
- **Constants**: son valors que posem directament. Els tipus de constants són:
  - **Numèriques**: es posen tal qual, amb punt decimal (no pot anar coma decimal, perquè serveix per a separar les columnes)
  - **Alfaumèriques**: es posen entre **cometes simples**
  - Per a altres tipus (com per exemple data-hora), posem la constant entre cometes simples, i PostgreSQL farà la conversió
- **Expressions** que utilitzen operadors per a combinar columnes, funcions, constants numèriques o alfanumèriques, ...

En la **<clàusula>** del **FROM** posarem la taula o les taules (separades per comes) d'on venen les dades.

Així el següent exemple trau tota la informació de la taula COMARQUES, és a dir totes les files i totes les columnes:

SELECT \* FROM COMARQUES;

Mentre que la següent només trau el nom:

SELECT nom\_c FROM COMARQUES;

En el següent exemple es trau el nom de cada població, els habitants, l'extensió i la densitat de població (habitants partit per extensió):

SELECT nom , poblacio , extensio , poblacio/extensio FROM POBLACIONS;

I en aquest traem el nom de cada poble, l'altura i la mitat de la seua altura (cosa un poc absurda però que serveix per a remarcar que si posem una constant numèrica, hem de posar el **punt decimal**, no la coma decimal, ja que la coma serveix per a separar els camps) :

SELECT nom , altura , altura \* 0.5 FROM POBLACIONS;

Exemples

1. Traure tota la informació de la taula POBLACIONS.

SELECT \* FROM POBLACIONS;



2. Traure el nom i l'altura de totes les poblacions.

SELECT nom, altura
`    `FROM POBLACIONS;



3. Traure el nom de les poblacions, el número d'habitants, i aquest número incrementat en un 5%.

SELECT nom, poblacio, poblacio \* 1.05 
`    `FROM POBLACIONS;

` `Observa com hem d'utilitzar el punt decimal i no la coma decimal, ja que la coma serveix per a separar els camps de la consulta SQL

4. Traure nom, latitud i els graus de la latitud de totes les poblacions. Per a traure els graus de la latitud traurem els caràcters de l'esquerra, fins el primer el caràcter º.

SELECT nom, latitud, SUBSTR(latitud,1,STRPOS(latitud,'º')-1)
`    `FROM POBLACIONS;



[« Anterior](8_la_consulta_select.md) | [Següent »](exercicis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
