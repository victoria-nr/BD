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

[« Anterior](exercicis6.md) | [Següent »](exercicis7.md)
# <a name="main"></a>**17. La clàusula LIMIT .. OFFSET**


Per mig de la clàusula **LIMIT - OFFSET** podrem fer que no apareguen totes les files que torna la sentència, sinó unes quantes.

- **LIMIT número**: especificarem quantes files volem que es tornen
- **OFFSET número**: especificarem a partir de quina posició volem que es tornen les files

Si no posem la part del OFFSET, apareixeran les primeres, i si especifiquem OFFSET, se saltaran les primeres, tantes com s'indica en OFFSET. Per a que realment tinga sentit aquesta clàusula, és conveninet ordenar la informació, ja que al dir les primeres ja s'està assumint que seran les primeres respecte algun ordre. Així, per exemple ens podrem plantejar traure coses com les 10 poblacions més altes, o les més habitades.

L'ordre implícit que acabem de comentar s'haurà de fer per mig de la clàusula ORDER BY. Així, si volem traure els clients més joves haurem d'ordenar per la data de naixement en ordre descendent, per a després traure els primenrs. Per tant és molt difícil veure una clàusula LIMIT si no tenim una clàusula ORDER BY.

**Nota**

En el SQL d'Access no existeix la clàusula LIMIT. Per a fer coses similar disposa del predicat **TOP**, que es posa immediatament després del SELECT, però sempre traurà les primeres, no té possibilitat d'OFFSET.



Sintaxi

SELECT <columnes>
FROM <taules>
[LIMIT *n*] [OFFSET *m*]



El número ***n*** ha de ser un enter, i se seleccionaran únicament les ***n*** primeres files (les de dalt). En cas de posat OFFSET se saltaran ***m*** files. En cas de no posar **LIMIT**, se saltaran ***m*** files i es trauran totes les altres fins el final.

Per exemple, si volem traure les 10 poblacions més altes, haurem d'agafar les 10 primeres, ordenant per altura en forma descendent:

SELECT nom , altura
FROM POBLACIONS
ORDER BY altura DESC
LIMIT 10

L'exemple anterior sembla correcte, però no funciona del tot bé perquè amb les dades que tenim, hi ha 3 poblacions que no tenen altura, i el valor nul el posa al final de tots els altres valors, en ordre ascendent, i per tant al principi en ordre descendent.

Ho podem arreglar senzillament saltant les 3 primeres (que són les del nul)

SELECT nom , altura
FROM POBLACIONS
ORDER BY altura DESC
LIMIT 10 OFFSET 3

Encara que sembla millor llevar les d'altura nula, així no estem obligats a saber quantes poblacions amb altura nula hi ha

SELECT nom , altura
FROM POBLACIONS
WHERE altura IS NOT NULL
ORDER BY altura DESC
LIMIT 10 

Si vulguérem traure totes les poblacions i altures, excepte les que tenen nul, i sabem que aquestes en són 3, podem posar OFFSET sense LIMIT, per a saltar les 3 primeres, i traure-les totes fins el final

SELECT nom , altura
FROM POBLACIONS
ORDER BY altura DESC
OFFSET 3

Exemples



1. Traure les 5 poblacions més poblades

SELECT nom , poblacio
FROM POBLACIONS
ORDER BY poblacio DESC
LIMIT 5



2. Traure les 4 comarques amb més pobles.

SELECT nom\_c , COUNT(\*)
FROM POBLACIONS
GROUP BY nom\_c
ORDER BY 2 DESC
LIMIT 4



3. Traure les 10 poblacions amb més instituts, saltant-nos les 3 primeres.

SELECT cod\_m , COUNT(\*)
FROM INSTITUTS
GROUP BY cod\_m
ORDER BY 2 DESC
LIMIT 10 OFFSET 3



[« Anterior](exercicis6.md) | [Següent »](exercicis7.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
