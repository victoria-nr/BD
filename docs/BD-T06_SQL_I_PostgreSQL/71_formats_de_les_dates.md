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

[« Anterior](7_funcions.md) | [Següent »](72_formats_dels_nmeros.md)
# <a name="main"></a>**7.1 Formats de les dates**
Aquest tipus és molt versàtil en quant al format, bé siga per a la introducció de les dades, o el que és més habitual, per a la seua presentació. S'haurà d'utilitzar una funció, **TO\_CHAR**, que acceptarà 2 paràmetres: el primer la data que es vol presentar, i el segon el format que volem. En el format indicarem per mig de determinats caràcters l'aspecte que volem. Per exemple, per a traure la data d'avui amb el format dia-mes-any, posaríem:

SELECT TO\_CHAR( NOW(), 'DD-MM-YYYY');

El següent quadre resumeix aquestos caràcters, agrupat per categories:

<table><tr><th colspan="2" valign="top"><b>DIES</b></th><th colspan="2" valign="top"><b>MESOS</b></th><th colspan="2" valign="top"><b>ANYS</b></th></tr>
<tr><td><b>D</b></td><td>Dia de la setmana (1-7)</td><td><b>MM</b></td><td>Mes (1-12)</td><td><b>Y</b></td><td>Últim dígit de l'any</td></tr>
<tr><td><b>DD</b></td><td>Dia del mes (1-31)</td><td><b>MONTH</b> </td><td>Mes en lletres, utilitzant 9 caràcters</td><td><b>YY</b> </td><td>Últims 2 dígits de l'any</td></tr>
<tr><td><b>DDD</b> </td><td>Dia de l'any (1-366)</td><td><b>MON</b> </td><td>Mes abreviat, utilitzant 3 caràcters</td><td><b>YYY</b> </td><td>Últims 3 dígits de l'any</td></tr>
<tr><td><b>DAY</b> </td><td>Dia de la setmana en lletres, utilitzant 9 caràcters</td><td><b>RM</b> </td><td>El mes amb números romans (juliol= VII)</td><td><b>YYYY</b> </td><td>Any amb 4 dígits</td></tr>
<tr><td><b>DY</b> </td><td>Dia de la setmana abreviat, utilitzant 3 caràcters</td><td> </td><td> </td><td></td><td> </td></tr>
</table>

En principi els formats que tornen lletres ho estaran en anglès, però després veurem com canviar d'idioma.

<table><tr><th colspan="2" valign="top"><b>HORES</b></th><th colspan="2" valign="top"><b>MINUTS</b></th><th colspan="2" valign="top"><b>SEGONS</b></th></tr>
<tr><td><b>HH , HH12</b> </td><td>Hora (1-12)</td><td><b>MI</b> </td><td>Minuts</td><td><b>SS</b> </td><td>Segons</td></tr>
<tr><td><b>HH24</b> </td><td>Hora (0-23)</td><td> </td><td> </td><td><b>SSSS</b> </td><td>Segons des de la mitjanit (0-86399)</td></tr>
<tr><td><b>PM , AM</b></td><td>Abans o després del migdia (AM i PM respectivament)</td><td> </td><td> </td><td> </td><td> </td></tr>
</table>



<table><tr><th colspan="6"><b>ALTRES</b></th></tr>
<tr><td><b>W , WW</b> </td><td>Setmana del mes (1-5) ; Setmana de l'any (1-53)</td><td><b>CC</b> </td><td>Segle, amb 2 xifres</td><td><b>Q</b> </td><td>Quart d'any, trimestre (1-4)</td></tr>
<tr><td colspan="6"> </td></tr>
<tr><td><b>/ , . ; : - <br><espai en blanc> <br>"text"</b> </td><td colspan="2">Caràcters que poden aparèixer acompanyant.</td><td colspan="3">En els formats que tornen lletres, poden eixir en majúscules, minúscules o la primera en majúscula, si així ho posem en les lletres del format.</td></tr>
<tr><td colspan="6">Si immediatament davant d'un format que torna lletres posem <b>FM</b>, eixiran els caràcters justos que ocupen (per exemple el dia de la setmana o el mes), i en els numèrics no eixiran els 0 no significatius.</td></tr>
<tr><td colspan="6">Si immediatament davant d'un format que torna lletres posem <b>TM</b>, ho traduirà a l'idioma que estiga configurat el servidor, però com el tenim configurat en anglès el resultat serà el mateix</td></tr>
</table>


Exemples:

Si ara fóra **9/1/16 13:39** (en el servidor, no en la vostra màquina), i férem **SELECT TO\_CHAR(NOW(),'*format*');**

|Format|Eixida|
| :- | :- |
|dd-mm-yy hh:mi|**09-01-23 01:39**|
|dd-mm-yy hh24:mi|**09-01-16 13:39**|
|dd-MON-yyy|**09-JAN-023**|
|dd-TMMON-yyy|**09-ENE-023  *(si el tinguérem configurat en espanyol)***|
|Day, dd "de" month "de" yyyy|**Monday , 09 de january de 2023   de 2016**|
|FMDay, dd "de" FMmonth "de" yyyy.|**Monday, 09 de january de 2023.**|
|TMDay, dd "de" TMmonth "de" yyyy.|**Lunes, 09 de enero de 2023.**    *(si el tinguérem configurat en espanyol)*|
|FMDy PM FMhh-FMmi-FMss|**Mon PM 1-39-00**|
|TMDy PM TMhh-TMmi-TMss|**Lun PM 01-39-00**  *(si el tinguérem configurat en espanyol)*|

[« Anterior](7_funcions.md) | [Següent »](72_formats_dels_nmeros.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
