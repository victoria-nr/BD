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

[« Anterior](exercicis4.md) | [Següent »](exercicis5.md)
# <a name="main"></a>**15. La clàusula ORDER BY**


Ordena les files del resultat respecte l'ordre especificat



Sintaxi

SELECT <columnes> 
FROM <taules> 
ORDER BY camp1 [ASC | DESC] { , camp2 [ASC | DESC] }

Ací tenim un exemple:

SELECT nom\_c, provincia 
FROM COMARQUES
ORDER BY nom\_c

S'ordenaran les files pel camp, en l'ordre marcat: ascendent o descendent (per defecte, ascendent). Si hi haguera un segon camp d'ordenació, aquest entraria en joc en cas de valors iguals del primer. Aquest segon podrà ser en ordre ascendent o descendent, independentment de l'ordre del primer camp.

SELECT nom\_c, provincia
FROM COMARQUES
ORDER BY provincia DESC, nom\_c

Es podrà ordenar per qualsevol camp de la taula, estiga indexada per aquest camp o no. L'avantatge d'estar indexada respecte a un camp és la rapidesa en l'ordenació. Així, si tenim una taula gran i ordenem per un determinat camp, es perdrà temps en aquesta ordenació. Si contínuament estem ordenant per aquest camp, perdrem aquest temps moltes vegades. Aleshores seria convenient crear un índex. Però hem de recordar que la creació d'un índex ocupa espai. Per tant no és bona solució indexar per tots els camps. Únicament, en tot cas, per aquells que més s'ordene. Veurem la creació d'índex en la tercera part d'aquest tema.

I es pot especificar en l'ordenació, una expressió que agafe un o més d'un camp amb operadors i funcions. Es pot posar un camp o una expressió que no estiga en la llista de camps o expressions que es volen visualitzar (al costat del SELECT), encara que normalment sí que ho visualitzarem, per a poder comprovar que realment està ordenat pel que s'ha especificat. Per exemple, si volem ordenar per la densitat d'habitants de les poblacions, que es calcula dividint el número d'habitants per l'extensió:

SELECT nom, poblacio, extensio
FROM POBLACIONS
ORDER BY poblacio/extensio DESC

Observeu que estem ordenant per un camp (**poblacio / extensio**) que no estem visualitzant, encara que seria molt més il·lustratiu mostrar-lo

Opcionalment, en el moment d'especificar el camp o l'expressió per la qual volem ordenar, si aquesta apareix en la llista de columnes a visualitzar, podrem posar senzillament el número d'ordre de la columna. Així, per exemple, podem fer el següent:

SELECT nom, poblacio, extensio, poblacio/extensio
FROM POBLACIONS
ORDER BY 4 DESC

On estem indicant que s'ordene de forma descendent per la quarta columna que va a visualitzar-se, és a dir, per **oblacio / extensio**

Hem d'observar que la clàusula ORDER BY és l'última, i que en cas d'haver clàusula GROUP BY, s'intentarà ordenar després d'haver agrupat. Per tant en cas de que la sentència continga un GROUP BY o s'haja utilitzat alguna funció d'agregat (que implica fer grups), només podrem posar en el ORDER BY camps que estiguen en el GROUP BY o que formen part d'una funció d'agregat. El raonament és el mateix que el fet en la clàusula GROUP BY o HAVING i l'error en cas de no respectar açò seria el matiex que el vist en aquell apartat.



Exemples

1. Traure tota la informació de les poblacions ordenades pel nom de la població.

SELECT \*
FROM POBLACIONS
ORDER BY nom



2. Traure tota la informació de les poblacions, ordenades pel nom de la comarca, i dins d'aquesta per l'altura (de forma descendent).

SELECT \*
FROM POBLACIONS
ORDER BY nom\_c, altura DESC



3. Traure les comarques amb el número de pobles i total d'habitants, d'aquelles que tenen més de 10 pobles, ordenades pel número de pobles, i dins d'aquest pel total de població de forma descendent.

SELECT nom\_c, COUNT(\*), SUM(poblacio)
FROM POBLACIONS
GROUP BY nom\_c
HAVING COUNT(\*) > 10
order by COUNT(\*) , SUM(poblacio) DESC

SELECT nom\_c, COUNT(\*), SUM(poblacio)
FROM POBLACIONS
GROUP BY nom\_c
HAVING COUNT(\*) > 10
order by 2 , 3 DESC



[« Anterior](exercicis4.md) | [Següent »](exercicis5.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
