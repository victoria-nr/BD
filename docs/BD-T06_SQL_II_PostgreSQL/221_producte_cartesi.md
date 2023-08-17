Bases de Dades

- [Tema 6: SQL - Consultes avançades (part II)](index.md)
- [2.1 Introducció](21_introducci.md)
- [2.2 Combinacions de taules](22_combinacions_de_taules.md) 
  - [2.2.1 Producte cartesià](221_producte_cartesi.md)
  - [2.2.2 Combinació interna](222_combinaci_interna.md) 
    - [Exercicis](exercicis.md)
  - [2.2.3 Combinació externa](223_combinaci_externa.md) 
    - [Exercicis](exercicis0.md)
- [2.3 Subconsultes](23_subconsultes.md) 
  - [Exercicis](exercicis1.md)
- [2.4 Consultes d'operacions de conjunts](24_consultes_doperacions_de_conjunts.md) 
  - [Exercicis](exercicis2.md)
- [Exercicis de tot el tema, amb els resultats](exercicis_de_tot_el_tema_amb_els_resultats.md)

[« Anterior](22_combinacions_de_taules.md) | [Següent »](222_combinaci_interna.md)
# <a name="main"></a>**2.2.1 Producte cartesià**


La manera més senzilla és posar les taules separades per comes, però segurament el resultat no és el que esperàvem.

Per exemple podem fer la següent sentència:

SELECT COMARQUES.nom\_c, nom 
FROM COMARQUES,POBLACIONS;

Nota

Observeu que hem posat el nom de la taula davant del camp **nom\_c**, perquè les dues taules tenen un camp amb aquest nom. Aquesta operació s'anomena **qualificació**. Si no qualificàrem amb el nom de la taula davant, hi hauria ambigüitat, no sabria a quin camp es refereix, si el d'una taula o el de l'altra. Quan els noms dels camps són diferents i per tant no coincideixen en les dues taules, no cal qualificar el camp (com per exemple amb el camp **nom**)

Si executem la sentència, veurem que tindrem un nombre de files inesperadament alt, **18.428 files !!!** I si analitzem les files veurem el perquè: s'ha combinat cada comarca amb tots els pobles (siguen de la comarca o no).

![](221_producte_cartesi.002.png)

Aquesta operació s'anomena **PRODUCTE CARTESIÀ** (***cross join***), i es caracteritza en què cadascuna de les files d'una taula es combina amb totes les files de l'altra taula. El nombre de files resultant serà, doncs, el resultat de multiplicar el nombre de files d'una taula pel nombre de files de l'altra taula (en el nostre cas 34 x 542 = 18428).

Rarament voldrem fer un producte cartesià. El més normal serà combinar una miqueta millor les taules. En el nostre exemple segurament ens interessarà molt més combinar *cada comarca amb les seues poblacions*.

[« Anterior](22_combinacions_de_taules.md) | [Següent »](222_combinaci_interna.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
