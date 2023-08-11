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

[« Anterior](5_dades_dels_exemples_i_els_exercicis.md) | [Següent »](7_funcions.md)
# <a name="main"></a>**6. Operadors**
Els operadors que es gasten en el SQL de PostgreSQL són moltíssims. Cada tipus de dades té una sèrie d'operadors, i el mateix operador, aplicat a tipus distints pot fer coses diferents.

Es poden veure tots els operadors en la taula **PG\_OPERATOR**, on tindrem el nom de l'operador, els tipus de dades dels operands i del resultat i el procediment que implementa l'operador. Ací tenim una vista d'aquesta taula, encara que hi ha tantíssims operadors que mareja i tot (els que estan repetits és per a especificar l'actuació sobre operands de diferents tipus).

![ref1]

Podríem fins i tot definir els nostres operadors, amb la sentència **CREATE OPERATOR**, on definiríem el tipus de l'operador de l'esquerra, el de la dreta, la funció que implementa l'operador, ... Ho intentarem en el tema següent, quan ja sapiguem crear funcions.

No farem un repàs extens de tots els operadors. Només els més habituals, i algun d'un tipus de dades especial. Els tipus de dades els veurem en la tercera part d'aquest tema, quan les sentències de creació de taules.

Per tant, fixeu-vos sobretot en els opradors **aritmètics**, de **cadena** i de **comparació**.

Operadors aritmètics

|**+**|Suma|**-**|Resta|**\***|Multiplicació|**/**|Divisió|
| :-: | :- | :-: | :- | :-: | :- | :-: | :- |
|**^**|Exponenciació|**|/**|Arrel quadrada|**!**|Factorial|**%**|Mòdul (rest de la divisió)|

Exemples

SELECT |/16;

SELECT 5 ^ 3;

SELECT 5!;



Operadors de cadena

|**||**|Concatenació|
| :-: | :- |

Exemples

SELECT 'Data i hora actual: ' || Now();

Operadors de comparació

|**=**|Igual|**<>**|Distint|**!=**|Distint|||
| :-: | :- | :-: | :- | :-: | :- | :-: | :- |
|**>**|Major|**>=**|Major o igual|**<**|Menor|**<=**|Menor o igual|

S'utilitzen principalment en les condicions. Tornen sempre un valor booleà (true o false)



Operador conversor de tipus

**:: *tipus***

Servirà per a convertir alguna dada a algun tipus de dades.

Així, per exemple,

- **'25-4-2012'::date** estem convertint una cadena de text en una dada de tipus date.
- **'(0,0)'::point** estem convertint el text a un punt.

La forma utilitzada en els exemples anteriors és una forma molt habitual de posar les constants d'un determinat tipus: la posem com a cadena de caràcters (entre cometes) i després la convertim. L'única restricció serà que PostgreSQL "entenga" el que hi ha entre cometes per fer la conversió.

Per veure que realment hi ha un canvi ens aprofitem de DBeaver que diu de quin tipus és un camp, si pot. Observeu que en el primer camp no hem posat més que una tira de caràcters, però en el segon intentem reconvertir aquesta mateixa tira de caràcters al tipus POINT. En el resultat s'observa com ha entés que el tipus de la dada és POINT.

![ref2]

També ens serviria la funció **point ('(0,0)')**

Operadors Geomètrics

|**Operador**|**Descripció**|**Utilització**|
| :-: | :- | :- |
|<->|Distància (han de ser del mateix tipus)|point '(1,0)' <-> point '(3,0)'|
|<@|Està contingut en?|'(1,1)'::point @ '((0,0),(2,2))'::box|
|@>|Conté?|box '((0,0),(2,2))' @> point '(1,1)'|

La llista d'operadors és molt més llarga, però ací només volem mostrar-ne algun a mode il·lustratiu.

Podem fer comprovacions d'aquest tipus:

SELECT '(0,0)'::point <-> '(3,4)'::point;

que ens donarà la **distància** entre el punt **(0,0)** i el punt **(3,4)**. Aquesta distància ha de ser 5.

SELECT '(1,1)'::point <@ '((0,0),2)'::circle;

que ens dirà si el **punt** **(1,1)** està **dins** del **cercle amb origen (0,0) i radi 2**. Com que sí que està tornarà el valor **true** (vertader).



[« Anterior](5_dades_dels_exemples_i_els_exercicis.md) | [Següent »](7_funcions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 6_operadors.002.png
[ref2]: 6_operadors.003.png
