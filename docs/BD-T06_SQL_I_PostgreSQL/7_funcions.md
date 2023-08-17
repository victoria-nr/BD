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

[« Anterior](6_operadors.md) | [Següent »](71_formats_de_les_dates.md)
# **7. Funcions**
Com veurem un poc més avant, en les sentències SQL, a banda de columnes i valors constants, podrem utilitzar funcions.

PostgreSQL té moltes funcions ja creades. 

Farem un recull de les funcions més importants de PostgreSQL, d'entre la multitud de funcions que existeixen. Les agruparem per categories.

Evidentment aquest recull no és per aprendre'l de memòria, sinó que servirà de consulta.



Funcions numèriques

|Funció |Explicació |Funció |Explicació |
| :-: | :-: | :-: | :-: |
|**ABS(n)**|Valor absolut de **n**.|**LOG(m,n)**|Logaritme, base **m**, de **n**|
|**ACOS(n)**|Arccosinus de **n** (invers del cosinus)|**MOD(m,n)**|La resta de la divisió entre **m** i **n**|
|**ASIN(n)**|Arcsinus de **n** (invers de sinus)|**POWER(m,n)**|**m** elevat a **n**|
|**ATAN(n)**|Arctangent de **n** (invers de la tangent)|**RANDOM()**|número aleatori entre 0 i 1|
|**CEIL(n)**|Enter immediatament superior o igual a **n**|**Round(n,[m])**|**n** arrodonit a **m** xifres decimals<br>(per defecte 0)|
|**COS(n)**|Cosinus de **n**.|**SIN(n)**|Sinus de **n**|
|**EXP(n)**|Exponencial de **n** (e<sup>n</sup>)|**SQRT(n)**|Arrel quadrada de **n**|
|**FLOOR(n)**|Enter immediatament inferior o igual a **n**|**TAN(n)**|Tangent de **n**|
|**LN(n)**|Logaritme neperià de **n**|**Trunc(n,[m])**|**n** truncat a **m** xifres decimals<br>(per defecte 0)|

Per exemple, podríem simular el llançament d'un dau d'aquesta manera:

SELECT TRUNC(RANDOM()\*6+1);



Funcions de caràcters

<table><tr><th valign="top">Funció </th><th valign="top">Explicació </th><th valign="top">Funció </th><th valign="top">Explicació </th></tr>
<tr><td><b>ASCII(c)</b></td><td>Torna el codi ASCII corresponent al caràcter <b>c</b></td><td><b>REPLACE(c1,c2,c3)</b></td><td>Reemplaça en <b>c1</b> cada ocurrència de <b>c2</b> per <b>c3</b></td></tr>
<tr><td><b>CHR(n)</b></td><td>Torna el caràcter amb codi ASCII <b>n</b>.</td><td><b>RPAD(c1,n[c2])</b></td><td>Torna <b>c1</b> reomplida per la dreta fins <b>n</b> caràcters amb la cadena <b>c2</b></td></tr>
<tr><td><b>CONCAT(c1,c2)</b></td><td>Concatena les dues cadenes (equivalent a l'operador <b>||</b>)</td><td><b>RTRIM(c1[,set])</b></td><td>Retalla per la dreta mentre troba la cadena set (per defecte blancs)</td></tr>
<tr><td><b>INITCAP(c1)</b></td><td>Torna la cadena amb la primera lletra de cada paraula en majúscules, i les altres en minúscules</td><td><b>STRPOS(s,s1)</b></td><td>Busca la primera ocurrència de la subcadena <b>s1</b> dins de la cadena <b>s</b></td></tr>
<tr><td><b>LENGTH(c1)</b></td><td>Llargària de la cadena. Si <b>c1</b> és de tipus CHAR, inclourà tots els espais en blanc del final.</td><td><b>SUBSTR(c1,m[,n])</b></td><td>Torna una subcadena de <b>c1</b> que comença en el caràcter <b>m</b> i consta de <b>n</b> caràcters (per defecte fins el final)</td></tr>
<tr><td><b>LPAD(c1,n[c2])</b></td><td>Torna <b>c1</b> reomplida per l’esquerra fins n caràcters amb la cadena <b>c2</b></td><td><b>TRANSLATE(c1,c2,c3)</b></td><td>Torna <b>c1</b> amb cada caràcter de <b>c2</b> substituït pel corresponent (en ordre) de <b>c3</b>.</td></tr>
<tr><td rowspan="2"><b>LTRIM(c1[,set])</b></td><td rowspan="2">Retalla per l’esquerra mentre troba la cadena set (per defecte blancs)</td><td><b>LOWER(c1)</b></td><td>Torna la cadena en minúscules</td></tr>
<tr><td><b>UPPER(c1)</b></td><td>Torna la cadena en majúscules</td></tr>
</table>

Per exemple, traurem els graus de la latitud de les poblacions. Haurem d'agafar els 2 primers caràcters (els de l'esquerra).

SELECT nom , latitud , SUBSTR(latitud,1,2)
FROM POBLACIONS;

Açò ho podríem millorar, ja que d'aquesta manera obliguem a que siguen sempre dos caràcters, els graus. De forma més genèrica, els graus és el que va davant del símbol **º**. Per tant el que podem fer és buscar aquest símbol i traure els de davant (des del primer fins a l'anterior a ell)

SELECT nom , latitud , SUBSTR(latitud,1,STRPOS(latitud,'º')-1)
FROM POBLACIONS;

Per agafar els minuts de forma senzilla seria traure els caràcters 4t i 5è, és a dir, 2 caràcters a partir del 4.

SELECT nom , latitud , SUBSTR(latitud,4,2)
FROM POBLACIONS;

Però de forma més genèrica (per si no s'han posat 0 no significatius), haurem de traure des de després del símbol **º** fins al caràctar anterior a **'** (la cometa) que assenyala els minuts. Tenim a més la dificultat afegida que la cometa justament és la manera d'especificar un text en SQL. Haurem de posar dos cometes per a escapar, i com que és un text va entre cometes. Resultat: 4 cometes.

SELECT nom , latitud , SUBSTR(latitud,STRPOS(latitud,'º')+1,STRPOS(latitud,'''')-STRPOS(latitud,'º')-1)
FROM POBLACIONS;

I el mateix faríem per als segons, (entre la cometa simple i la doble).

Aquesta sentència resumeix l'anterior, separant graus, minuts i segons.

SELECT nom, latitud,
SUBSTR(latitud,1,STRPOS(latitud,'º')-1),
SUBSTR(latitud,STRPOS(latitud,'º')+1,STRPOS(latitud,'''')-STRPOS(latitud,'º')-1),
SUBSTR(latitud,STRPOS(latitud,'''')+1,STRPOS(latitud,'"')-STRPOS(latitud,'''')-1)
FROM POBLACIONS;

Funcions de data

<table><tr><th>Funció</th><th colspan="2" valign="top">Explicació</th></tr>
<tr><td><b>NOW() (CURRENT_TIMESTAMP)</b></td><td valign="top">Torna la data-hora actual, amb la diferència d'hores respecte la GMT</td><td rowspan="5" valign="top">Totes les funcions que tornen hores (amb data o sense), ho faran fins la micra de segon, a no ser que entre parèntesi indiquem les xifres decimals (de segon) que volem</td></tr>
<tr><td><b>LOCALTIMESTAMP</b></td><td valign="top">Igual que l'anterior, però sense la diferència de la GMT</td></tr>
<tr><td><b>CURRENT_DATE</b></td><td valign="top">Torna la data actual</td></tr>
<tr><td><b>CURRENT_TIME</b></td><td valign="top">Torna l'hora actual (amb diferència GMT)</td></tr>
<tr><td valign="top"><b>LOCALTIME</b></td><td valign="top">Torna l'hora actual (sense diferència GMT)</td></tr>
<tr><td><b>AGE(t)</b></td><td colspan="2" valign="top">Torna la diferència de la data actual i <b>t</b></td></tr>
<tr><td><b>AGE(t1,t2)</b></td><td colspan="2" valign="top">Torna la diferència entre <b>t1</b> (posterior) i <b>t2</b> (anterior)</td></tr>
<tr><td><b>EXTRACT(camp FROM t)</b></td><td colspan="2" valign="top">Trau el número corresponent al <b>camp</b> (que pot ser <b>year</b>, <b>month</b>, <b>day</b>, <b>hour</b>, <b>minute</b>, <b>second</b>, <b>millisecond</b>, <b>microsecond</b>, <b>dow</b> (<b>day of week</b>), ...</td></tr>
</table>
Per exemple, ¿quan de temps ha passat des de l'intent de cop d'estat?

SELECT AGE('1981/02/23'::DATE);

O un altre, ¿en quin any estem?

SELECT EXTRACT(year FROM CURRENT\_DATE);

Funcions geomètriques

|Funció|Explicació|Funció|Explicació|
| :-: | :-: | :-: | :-: |
|**AREA(o)**|Àrea de l'objecte|**HEIGTH(r)**|Altura del rectàngle|
|**CENTER(o)**|Centre de l'objecte|**RADIUS(c)**|Radi del cercle|
|**DIAMETER(c)**|Diàmetre del cercle|**WIDTH(r)**|Amplària del rectàngle|

Per exemple, l'àrea d'un cercle:

SELECT AREA('((5,5),2)'::CIRCLE);



Funcions IP

|Funció|Explicació|Exemple|Resultat|
| :-: | :-: | :-: | :-: |
|**HOST(ip)**|Trau en format text l'adreça IP|HOST('192.168.2.15/24')|192\.168.2.15|
|**MASKLEN(ip)**|Trau el número de bits de la màscara|||

**This document was truncated here because it was created in the Evaluation Mode.**
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
