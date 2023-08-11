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

[« Anterior](71_formats_de_les_dates.md) | [Següent »](8_la_consulta_select.md)
# <a name="main"></a>**7.2 Formats dels números**




També podrem utilitzar la funció **TO\_CHAR** per a donar l'aspecte que vulguem als números. En la següent taula tenim un resum amb els diferents símbols, un comentari descriptiu de cada símbol, i un exemple de format amb el resultat que donaria per a un determinat valor. La sentència seria **SELECT TO\_CHAR(***valor***,'***format***');**: 

|<h3>**Símbol**</h3>|<h3>**Comentari**</h3>|<h3>**Format**</h3>|<h3>**Valor**</h3>|<h3>**Resultat**</h3>|
| :-: | :- | :-: | :-: | :-: |
|**9**|Equival a una xifra decimal. Torna el valor amb el número de xifres especificades, substituint els zeros no significatius per espais en blanc. Únicament no substitueix per espais en blanc quan el valor és 0. Els negatius els treu amb el signe, i els positius sense. |**9999** |34<br>-34 |34<br>-34 |
|**0**|Igual a l'anterior, però sense substituir els zeros no significatius per espais en blanc. |**0000** |34<br>-34 |0034<br>-0034 |
|**S**|Treu el signe: - per als negatius, + per als positius. |**S9990** |34<br>-34 |+34<br>-34 |
|**$**|Treu aquest símbol. |**$9990** |34 |$ 34 |
|**.**|Treu el punt decimal en la posició indicada |**9990.99<br><br>9999\.99**|34<br>0\.5<br>0\.5 |34\.00<br>0\.50<br>.50 |
|**,**|Treu la coma separadora de milers |**9,999,990.99**|34<br>1234\.5<br>1234567 |34\.00<br>1,234.50<br>1,234,567.00 |
|**€**|Treu el símbol monetari de l'euro |**9990€** |34 |34€ |
|**D**|Treu el símbol separador de la part decimal del país |**9990D99** |34<br>0\.5 |34,00<br>0,50 |
|**G**|Treu el símbol separador dels milers del país en la posició indicada |**9G999G990D99<br><br>9G990D99** |1234<br>1234567<br>1234\.5 |1\.234,00<br>1\.234.567,00<br>1\.234,50 |
|**RN**|Treu el valor en números romans (fins el 3999). |**RN <br>rn** |1967 |MCMLXVII<br>mcmlxvii |

[« Anterior](71_formats_de_les_dates.md) | [Següent »](8_la_consulta_select.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
