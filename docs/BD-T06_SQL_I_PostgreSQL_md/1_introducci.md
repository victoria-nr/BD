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

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_ddl_i_dml.md)
# <a name="main"></a>**1. Introducció**


**SQL** és un llenguatge per a organitzar, gestionar i recuperar dades emmagatzemades en una Base de Dades. El nom "**SQL**" és una abreviatura de ***Structured Query Language*** (Llenguatge Estructurat de Consultes), i com el seu nom indica, és un llenguatge informàtic que es pot utilitzar per a interaccions amb una Base de Dades de tipus relacional.

SQL s'utilitza per a controlar totes les funcions que un SGBD proporciona als seus usuaris, incloent:

- ***Definició de dades***. SQL permet a un usuari definir l'estructura i organització de les dades emmagatzemades i les relacions existents entre elles (claus externes).
- ***Recuperació de dades***. SQL permet a un usuari o a un programa d'aplicació recuperar les dades emmagatzemades de la base de dades i utilitzar-les.
- ***Manipulació de dades***. SQL permet a un usuari o a un programa d'aplicació actualitzar la base de dades afegint noves dades, suprimint dades antigues i modificant dades prèviament emmagatzemades.
- ***Control d'accés***. SQL pot ser utilitzat per a restringir la capacitat d'un usuari per a recuperar, afegir i modificar dades, protegint així les dades guardades davant d'accessos no autoritzats.
- ***Compartició de dades***. SQL s'utilitza per a coordinar la compartició de dades per part d'usuaris concurrents, assegurant que no interfereixen entre ells.
- ***Integritat de dades***. SQL defineix restriccions d'integritat en la base de dades, protegint-la contra corrupcions causades per actualitzacions inconsistents o per fallades del sistema.

SQL no és realment un llenguatge informàtic complet tal com JAVA, C o Python. SQL no disposa de la sentència *IF* per a examinar condicions, ni de les sentències *WHILE* o *FOR* per a fer bucles, per exemple. En compte d'això, SQL és un subllenguatge de base de dades, que consta d'unes trenta sentències especialitzades per a tasques de gestió de bases de dades, però **només 7 són les sentències principals**.

També es diu que és un llenguatge de **quarta generació** perquè en ell es diu quina informació es vol, sense especificar exactament com s'aconsegueix aquesta informació.

També es diu que és un llenguatge orientat a **conjunt de registres**, ja que una sentència pot tornar un conjunt de registres. Açò és un gran avantatge amb els llenguatges de tercera generació, que només podien treballar registre a registre.

Dues són les maneres d'executar sentències SQL.

- **De forma interactiva**: s'escriu una sentència SQL, i s'executa, tornant normalment un conjunt de registres que es presentaran en forma tabular. En **Access** el lloc on procedir d'aquesta manera és en les **consultes**, triant ***Vista SQL***. Tindrem lloc per escriure la sentència tal i com es mostra en la primera imatge. En la segona imatge, es mostra una consulta ja feta en el tema anterior, però veient-la en SQL. En la tercera hem executat la consulta:

|![ref1]|![ref2]|![ref3]|
| :-: | :-: | :-: |

- **Dins d'un programa** escrit en un altre llenguatge, que actuarà com llenguatge amfitrió (i el SQL seria el llenguatge host, "*huesped*"). En el cas de Access podríem incloure sentències SQL en Visual Basic. D'aquesta manera s'estén el llenguatge amfitrió i li permet accedir a la Base de Dades.

SQL és el llenguatge estàndard d'accés i manipulació de Bases de Dades dels Sistemes Gestors de Bases de Dades Relacionals. A tots, absolutament a tots els SGBD Relacionales comercials es pot accedir per SQL.

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_ddl_i_dml.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 1_introducci.002.png
[ref2]: 1_introducci.003.png
[ref3]: 1_introducci.004.png
