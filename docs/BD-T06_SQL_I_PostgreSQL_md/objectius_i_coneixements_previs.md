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

[« Anterior](index.md) | [Següent »](1_introducci.md)
# <a name="main"></a>**Objectius i Coneixements previs**
![ref1]
## **Objectius**
L'objectiu primordial és **dominar el llenguatge SQL**, per a poder fer sentències de dificultat mitjana-alta. En particular s'hauran de saber fer:

- Consultes DDL per a crear, modificar i esborrar taules i vistes.
- Consultes DML per a inserir, modificar o esborrar files d'una taula.
- Consultes SELECT, per a traure informació de les taules. Concretament s'haurà de conéixer a la perfecció totes les seues clàusules.
- Consultes SELECT amb combinacions o reunions de taules, incloent les combinacions externes (LEFT JOIN).
- Consultes d'unió
- Subconsultes

Un altre objectiu és el de conèixer l'arquitectura **client-servidor**, i per a aconseguir açò treballarem en **PostgreSQL**. Mentre que en **Access** cadascú tenia la seua pròpia Base de Dades, ara en PostgreSQL la Base de Dades està en un únic lloc remot, en el servidor. I tots ens connectem com a usuaris al servidor (com a clients). Per ser més conscients, ens connectarem com el mateix usuari a la mateixa Base de Dades, compartint per tant les dades, excepte quan ens toque crear objectes, que cadascú es connectarà com un usuari diferent a una Base de Dades diferent, per a no interferir els uns amb els altres.

Per l'extensió del tema, el dividirem en 3 parts.

- Per motius didàctics començarem per la sentència SELECT, en la seua forma més senzilla.
- Continuarem amb les consultes més complicades del SELECT.
- Per últim veurem les sentències DDL i les de manipulació de dades.

![ref1]
## **Coneixements previs**
Els coneixements previs estrictes del tema és el Model Relacional, encara que no el podrem deslligar de tot l'entorn que ens estem construint a l'hora de dissenyar una Base de Dades, i així el tema del Model Entitat-Relació també ens vindrà molt bé. I  per a poder practicar ens fa falta un SGBD. S'ha optat per un SGBD nou no vist encara, **PostgreSQL**, pel comentat en el punt anterior. Com és la primera vegada que es veu, no hi ha coneixements previs de cap entorn d'aquest SGBD.

[« Anterior](index.md) | [Següent »](1_introducci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: objectius_i_coneixements_previs.002.png
