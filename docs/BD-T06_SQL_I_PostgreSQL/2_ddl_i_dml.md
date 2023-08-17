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

[« Anterior](1_introducci.md) | [Següent »](3_client_dbeaver_installaci_i_confiuraci.md)
# <a name="main"></a>**2. DDL i DML**


Com s'ha comentat en la pregunta anterior, SQL ens permet definir, controlar i accedir a una Base de Dades.

Farem una distinció principal entre aquestes funcions, separant el que són les estructures de les taules i el contingut de les taules. En aquest sentit tindrem 2 subtipus de llenguatges:

- **DDL** (*Data Definition Language* o *Llenguatge de Definició de Dades*): permet definir, modificar o esborrar les estructures, com poden ser taules, vistes, índex, ... i fins i tot Bases de Dades. Bàsicament les sentències són 3: 

|**CREATE** |per a crear l'estructura|
| :- | :- |
|**ALTER** |per a modificar-la|
|**DROP** |per a esborrar-la|

- **DML** (*Data Manipulation Language* o *Llenguatge de Manipulació de Dades*): permet accedir al contingut de les estructures, a les dades. Aquest accés pot ser de dos tipus: per a consultar o per a modificar les dades 

  Per a consultar:
  **SELECT** 

  Per a modificar 

|**INSERT**|insereix noves files|
| :- | :- |
|**UPDATE** |modifica el contingut de files ja existents|
|**DELETE**|esborra files|

El llenguatge SQL és més extens que les sentències anteriors, incorporant també el que s'anomena **DCL** (*Data Control Language* o *Llenguatge de Control de Dades*), que permet controlar les dades per a donar permisos o llevar-los sobre les dades, o controlar les transaccions, ..., però de moment ens aconformarem amb les sentències de DML i DDL, i aquestes últimes, sobretot, per a definir taules.

[« Anterior](1_introducci.md) | [Següent »](3_client_dbeaver_installaci_i_confiuraci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
