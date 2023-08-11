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

[« Anterior](19_ordre_amb_qu_sexecuta_una_sentncia_sql.md)
# <a name="main"></a>**Exercicis de tot el tema, amb els resultats**
En la BD **factura**, connectant com a usuari **factura**:

**6.1** Traure tota la informació dels pobles (anomeneu-la **Ex\_6\_1.sql**).

![ref1]

Un total de **1663 files**

**6.2** Traure el codi postal, el nom i l'adreça, per aquest ordre, de tots els venedors (anomeneu-la **Ex\_6\_2.sql**).

![ref2]

**6.3** Traure el codi d'article, la descripció, preu i preu incrementat en un 5%, de tots els articles.

![ref3]

Un total de **812 files**

**6.4** Traure la informació dels clients amb el següent format (ha d'anar tot en una columna):

**Damborenea Corbato, Alicia. CALLE MADRID, 83 (12425)**

Fixeu-vos que està tot en una columna, i per tant haureu de concatenar de la forma adequada. Fixeu-vos també que en en el nom només les inicials estan en majúscules

![ref4]

Un total de **49 files**

**6.5** Traure el num\_f, data i cod\_ven de les factures amb les següents capçaleres respectivament: **Número Factura**, **data** i **Codi Venedor** (anomeneu-lo **Ex\_6\_5**)

![ref5]

Un total de **105 files**

**6.6** Donar àlias als camps que ho necessiten de la taula ARTICLE (anomeneu-lo **Ex\_6\_6**)

![ref6]

Un total de **812 files**

**6.7** Traure els **clients** de la **ciutat** amb codi **12309**.

![ref7]

**6.8** Traure totes les **factures** del mes de **març** de **2015**.

![ref4]

**6.9** Traure tots els articles de la **categoria** **BjcOlimpia** amb un **stock** entre **2** i **7** unitats.

![ref8]

**6.10** Traure tots els **clients** que **no** tenen introduït el **codi postal**.

![ref9]

**6.11** Traure tots els **articles** amb el **stock** introduït però que **no** tenen introduït el **stock mínim**.

![ref10]

**6.12** Traure tots els **clients**, el **primer cognom** dels quals és **VILLALONGA**.

![ref11]

**6.13.a** Modificar l'anterior per a traure tots els que són **VILLALONGA** de **primer** o de **segon** cognom.

![ref12]

**6.13.b** Modificar l'anterior per a traure tots els que **no** són **VILLALONGA** ni de primer ni de segon cognom.

![ref4]

Un total de **46 files**

**6.14** Traure els **articles** "**Pulsador**" (la descripció conté aquesta paraula), el **preu** dels quals oscila entre **2 i 4 €** i dels quals tenim un **stock** estrictament **major** que el **stock mínim**.

![ref13]

**6.15** Comptar el nombre de **clients** que tenen el **codi postal nul**.

![ref4]

**6.16** Comptar el número de vegades que l'article **L76104** entra en les línies de factura, i el número total d'unitats venudes d'aquest article. Només us fa falta la taula LINIA\_FAC.

![ref4]

**6.17** Traure la **mitjana** del **stock** dels articles.

![ref14]

**6.18** Modificar l'anterior per a **tenir en compte els valors nuls, com si foren 0**. Us vindrà bé la funció **COALESCE** que converteix els nuls del primer paràmetre al valor donat com a segon paràmetre (si és diferent de nul, deixa igual el valor). Per tant l'heu d'utilitzar d'aquesta manera: **COALESCE(stock,0)**

![ref15]

**6.19** Comptar **quantes factures** té el client **375**

![ref4]

**6.20** Calcular el **descompte màxim**, el **mínim** i el descompte **mitjà** de les **factures**.

![ref4]

**6.21** Comptar el número de pobles de cada província (és suficient traure el codi de la província i el número de pobles).

![ref4]

**6.22** Comptar el nombre de clients en cada poble i codi postal.

![ref16]

Un total de **45 files**

**6.23** Comptar el número de factures de cada venedor a cada client.

![ref17]

Un total de **96 files**

D'aquestes 96 files, relativament poque tenen un valor diferent de 1 en el número de factures: la fila 29 (455, 30, 2) o la fila 34 (5, 342, 3)

**6.24** Comptar el número de factures de cada trimestre. Per a poder traure el trimestre i agrupar per ell (ens val el número de trimestre, que va del 1 al 4), podem utilitzar la funció **TO\_CHAR(data,'Q')**.

![ref4]

No apareix ordenat, i vol dir que en el trimestre 2 hi ha 25 factures, en el trimestre 4 hi ha 25, en el trimestre 3 hi ha 33 i en el trimestre 1 hi ha 22

**6.25** Calcular quantes vegades s'ha venut un article, la suma d'unitats venudes, la quantitat màxima i la quantitat mínima.

![ref4]

Un total de **399 files**

**6.26** Comptar el número d'articles de cada categoria i el preu mitjà.

![ref18]

**6.27** Calcular el total de cada factura, sense aplicar descomptes ni IVA. Només ens farà falta la taula **LINIES\_FAC**, i consistirà en agrupar per cada **num\_f** per a calcular la suma del **preu** multiplicat per la **quantitat**.

![ref4]

Un total de **105 files**

**6.28** Calcular la mitjana de quantitats demanades d'aquells articles que s'han demanat més de dues vegades. Observeu que la taula que ens fa falta és LINIA\_FAC, i que la condició (en el HAVING) és sobre el número de vegades que entra l'article en una linia de factura, però el resultat que s'ha de mostrar és la mitjana de la quantitat.

![ref19]

**6.29** Traure els pobles que tenen entre 3 i 7 clients. Traure només el codi del poble i aquest número

![ref20]

**6.30** Traure les categories que tenen més d'un article "car" (de més de 100 €). Observeu que també ens eixirà la categoria NULL, és a dir, apareixerà com una categoria aquells articles que no estan catalogats.

![ref21]

**6.31** Traure els clients que tenen més d'una factura, amb el número de factures.

![ref22]

Un total de **33 files**

**6.32** Modificar l'anterior per a traure els clients que tenen més d'una factura en el primer trimestre.

![ref4]

**6.33** Calcular el total de cada factura d'aquelles factures que tenen 10 o més línies de factura, sense aplicar descomptes ni IVA (com la consulta **6.26**), i també aplicant el descompte que consta en la línia de factura (no el descompte de tota la factura). Tindrem el problema que el valor NULL és especial, i en operar amb qualsevol altre valor donarà NULL. En aquest cas clarament l'hem de considerar com un descompte 0. Podeu utilitzar una funció que substitueix els valors nuls trobats en el primer paràmetre, pel segon paràmetre d'aquesta manera: **COALESCE(dte,0)**

![ref23]

**6.34** Traure tots els clients ordenats per codi de població, i dins d'aquestos per codi postal.

![ref4]

Un total de **49 files**

**6.35** Traure tots els articles ordenats per la categoria, dins d'aquest pel stock, i dins d'aquest per preu (de forma descendent)

![ref4]

Un total de **812 files**

**6.36** Traure els resultats de la consulta **6.33** ordenats pel total de la factura quan ja s'ha aplicat el descompte, de forma descendent.

![ref24]

**6.37** Traure tots els articles ordenats per la diferència entre el stock i el stock mínim de forma descendent. Com que en moltes ocasions el stock o el stock mínim és nul, hem de considerar en aquestos casos com 0. Per tant hem de tornar a utilitzar la funció **COALESCE(stock,0)** (i també per al stock mínim).

![ref4]

Un total de **812 files**

**6.38** Traure els codis de venedor amb el número de factures venudes en el segon semestre de 2015, ordenades per aquest número de forma descendent

![ref4]

**6.39** Traure els venedors que han venut alguna cosa el mes de gener de 2015.

![ref4]

**6.40** Traure els diferents tipus d'IVA que s'han aplicat a les factures de cada venedor, també durant el mes de gener de 2015

![ref4]

**6.41** Traure els diferents caps de venedors (eviteu que aparega el valor nul)

![ref4]

**6.42** Traure els diferents descomptes que s'han aplicat als articles, el codi dels quals comença per **SAT**. Traure tant el codi d'article com el descompte.

![ref4]

**6.43** Comptar en quantes poblacions tenim clients

![ref4]

**6.44** Traure tota la informació dels dos articles més cars.

![ref4]

**6.45** Traure el codi de les tres ciutats amb més clients

![ref4]

**6.46** Traure el venedor que ha venut menys factures

![ref4]

**6.47** Traure les tres factures més cares (sense comptar els descomptes)

![ref25]

**6.48** Modificar l'anterior per a traure totes les factures, excepte les 3 més cares.

![ref4]

Un total de **102 files**

**6.49** Crear una taula anomenada **ARTICLE\_999x**, on 999 han de ser les 3 últimes xifres del DNI, i x la lletra del teu NIF, que siga una còpia de la taula ARTICLE, però substituint els valors nuls de **stock** i **stock\_min** per zeros.

El resultat ha de ser la creació de la taula. Si consulteu el seu contingut ha de ser el següent:

![ref26]

Untotal de **812 files**

**6.50** Utilitzar la taula anterior per a traure el stock màxim, el mínim i la mitjana de stocks. Observeu que si utilitzàrem la taula ARTICLE, els resultats no serien els mateixos (excepte el màxim), sobretot la mitjana, ja que els valors nuls no entrarien en els càlculs d'aquesta mitjana.

![ref4]

[« Anterior](19_ordre_amb_qu_sexecuta_una_sentncia_sql.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis_de_tot_el_tema_amb_els_resultats.002.png
[ref2]: exercicis_de_tot_el_tema_amb_els_resultats.003.png
[ref3]: exercicis_de_tot_el_tema_amb_els_resultats.004.png
[ref4]: exercicis_de_tot_el_tema_amb_els_resultats.005.png
[ref5]: exercicis_de_tot_el_tema_amb_els_resultats.006.png
[ref6]: exercicis_de_tot_el_tema_amb_els_resultats.007.png
[ref7]: exercicis_de_tot_el_tema_amb_els_resultats.008.png
[ref8]: exercicis_de_tot_el_tema_amb_els_resultats.009.png
[ref9]: exercicis_de_tot_el_tema_amb_els_resultats.010.png
[ref10]: exercicis_de_tot_el_tema_amb_els_resultats.011.png
[ref11]: exercicis_de_tot_el_tema_amb_els_resultats.012.png
[ref12]: exercicis_de_tot_el_tema_amb_els_resultats.013.png
[ref13]: exercicis_de_tot_el_tema_amb_els_resultats.014.png
[ref14]: exercicis_de_tot_el_tema_amb_els_resultats.015.png
[ref15]: exercicis_de_tot_el_tema_amb_els_resultats.016.png
[ref16]: exercicis_de_tot_el_tema_amb_els_resultats.017.png
[ref17]: exercicis_de_tot_el_tema_amb_els_resultats.018.png
[ref18]: exercicis_de_tot_el_tema_amb_els_resultats.019.png
[ref19]: exercicis_de_tot_el_tema_amb_els_resultats.020.png
[ref20]: exercicis_de_tot_el_tema_amb_els_resultats.021.png
[ref21]: exercicis_de_tot_el_tema_amb_els_resultats.022.png
[ref22]: exercicis_de_tot_el_tema_amb_els_resultats.023.png
[ref23]: exercicis_de_tot_el_tema_amb_els_resultats.024.png
[ref24]: exercicis_de_tot_el_tema_amb_els_resultats.025.png
[ref25]: exercicis_de_tot_el_tema_amb_els_resultats.026.png
[ref26]: exercicis_de_tot_el_tema_amb_els_resultats.027.png
