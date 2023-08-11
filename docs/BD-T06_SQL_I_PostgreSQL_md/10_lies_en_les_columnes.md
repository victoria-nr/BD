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

[« Anterior](exercicis.md) | [Següent »](exercicis0.md)
# <a name="main"></a>**10. Àlies en les columnes**


Tenim també la possibilitat de donar noms (***àlies***) a les columnes que apareixeran en la capçalera de les columnes corresponents en el resultat.



Sintaxi

SELECT columna1 [AS àlias1] [ , columna2 [AS àlias2] ] 

FROM TAULA;



Si volem que en la capçalera apareguen més d'una paraula, les haurem de tancar amb cometes dobles ( **"** ).

Per exemple:

SELECT cod\_m AS "Codi Municipi" , nom 
FROM POBLACIONS;

És especialment útil la utilització d'àlies quan posem una expressió, en compte d'una única columna. Si no posem àlies, apareix en la capçalera una cosa semblant a **?column?**.

SELECT nom\_c || ' (' || provincia || ')' AS " Comarca (provincia)"
FROM COMARQUES;

I a banda del seu valor estètic, més avant veurem sentències SQL en les quals obligatòriament haurem de posar àlies a les columnes que siguen el resultat d'una expressió.

Exemples

1. Traure de les poblacions, el nom i el número d'habitants (camp poblacio), aquest últim el nom **habitants**.

SELECT nom, poblacio AS habitants
FROM POBLACIONS;



2. Traure tots els camps de la taula INSTITUTS de forma elegant.

SELECT codi AS "Codi Institut", nom as Nom, adreca AS Adreça, numero AS Número, codpostal AS "Codi Postal", cod\_m AS "Codi Municipi"
FROM INSTITUTS;

` `Si volem que totes les capçaleres comencen per majúscula, haurem de posar tots els àlies entre cometes dobles, encara que només consten d'una paruala

SELECT codi AS "Codi Institut", nom as "Nom", adreca AS "Adreça", numero AS "Número", codpostal AS "Codi Postal", cod\_m AS "Codi Municipi"
FROM INSTITUTS;

[« Anterior](exercicis.md) | [Següent »](exercicis0.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
