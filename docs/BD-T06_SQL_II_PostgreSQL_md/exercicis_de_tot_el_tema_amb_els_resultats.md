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

[« Anterior](exercicis2.md)
# <a name="main"></a>**Exercicis de tot el tema, amb els resultats**
**6.51** Traure el nom dels clients amb el número de factura i la data (individuals, sense agrupar res) que té cada client. Trau el resultat ordenat per client, i dins d'aquest per data de la factura

![ref1]

Un total de **105 files**

**6.52** Traure el nom del soci, amb el codi i la descripció de cada article que ha demanat. Ordena per nom del soci i codi de l'article.

![ref2]

Un total de **541 files**

**6.53** Modificar l'anterior per a que no es repetesquen els resultats.

![ref3]

Un total de **532 files**

Observa com ara no es repeteix la fila 10 i 11, i abans sí

**6.54** Traure el nom dels clients amb la quantitat de factures que tenen, ordenades per aquest número de major a menor

![ref4]

Un total de **40 files**

**6.55** Traure el número de factura, data, codi de client, total de la factura (amb l'àlies IMPORT) i total de la factura aplicant descomptes d'article (amb àlies DESCOMPTE\_1), com en la consulta **6.33**, però sense el límit de les 10 línies de factura. Ordena per número de factura.

![ref5]

Un total de **105 files**

**6.56** Modificar l'anterior per a aplicar també el descompte de la factura (amb l'àlies DESCOMPTE\_2)

![ref6]

Un total de **105 files**

**6.57** Traure el codi i nom d'aquells venedors que supervisen algú (consten com a cap). Traure també el número de supervisats de cadascun d'aquestos supervisors.

![ref7] 

**6.58** Traure el codi i descripció dels articles juntament amb el número de vegades que s'ha venut, el total d'unitats venudes i la mitjana d'unitats venudes per factura. Ordenar pel número total d'unitats venudes de forma descendent, i dins d'aquesta per codi d'article de forma ascendent.

![ref5]

Un total de **399 files**

**6.59** Traure el codi i la descripció de les categories, amb la quantitat d'articles venuts de cada categoria, d'aquelles categories de les quals se n'han venut més de 100 unitats. Ordenar per aquest número de forma descendent.

![ref8]

**6.60** Traure el codi i el nom dels clients que no tenen cap factura.

![ref9]

**6.61** Traure el codi, descripció i total d'unitats venudes de tots els articles, fins i tot d'aquells que no s'ha venut res.

**Nota**

Per a deixar-lo més bonic, com que la suma de valors nuls no és 0 sinó nul, per a que ens aparegue el valor 0 podem utilitzar la funció COALESCE(*valor*,0), que si el valor és nul torna un 0.

![ref5]

Un total de **812 files**

**6.62** Traure el nom de tots els pobles i el número de clients en cas que en tinguen. Ordena per número de clients de forma descendent.

![ref10]

Un total de **1663 files**

**6.63** Traure el codi i la descripció de les categories, amb el número d'articles de cada categoria i el número total d'unitats venudes de cada categoria, d'aquelles categories de les quals tenim més de 15 articles, i ordenat per número d'articles de forma descendent. Aquesta sentència ja és prou complicada. Concretament haureu de tenir en compte que:

- Voldrem traure el número d'articles de cada categoria, però potser alguns articles no s'han venut, i per tant no apareixeran en la taula LINIA\_FAC.
- I també tenim el problema que, com ens fa falta la taula LINIA\_FAC, un article venut en més d'una factura apareixerà més d'una vegada. Si comptem de forma normal, el comptaríem més d'una vegada cada article. Per tant voldrem comptar els diferents articles de cada categoria.

![ref5]

**6.64** Traure el número màxim de factures fetes a un client

![ref11]

**6.65** Traure el l'import que suposa la factura més cara i l'import que suposa la més barata (sense considerar ni descomptes ni IVA)

![ref12]

**6.66** Traure el número de factures més alt que s'ha venut per venedor en cada trimestre (no traurem qui és el venedor, que seria encara més complicat). Per a poder agrupar per trimestre, ens farà falta la funció **TO\_CHAR(data,'Q')**, que trau el número de trimestre. El pas previ és calcular el número de factures de cada venedor i en cada trimestre. Després, amb la informació anterior, voldrem calcular el màxim de cada trimestre.

![ref13]

**6.67** Traure els articles més cars que la mitjana. Tragueu-los ordenats per la categoria, i després per codi d'article.

![ref14]

Un total de **164 files**

**6.68** Modificar l'anterior per a traure els articles més cars que la mitjana de la seua categoria. Tragueu-los ordenats per la categoria

![ref5]

Un total de **75 files**

És un resultat molt similar a l'anterior, però observeu que ara no estan els productes de les files 5, 14, 15, ...

**6.69** Traure els pobles on tenim clients però no tenim venedors. Ha de ser per mig de subconsultes (en plural). Ordeneu per codi del poble.

![ref15]

**6.70** Traure els pobles on tenim més venedors que clients. Traure el codi del poble, el nom i el número de venedors. Ordena per nom del poble.

![ref16]

**6.71** Traure l'import de la factura més cara de cada trimestre. La informació prèvia és la factura amb la data i l'import. A partir d'ahí haurem de calcular el màxim de l'import per a cada trimestre (no caldrà traure quina factura és).

![ref17]

**6.72** Traure el nom del venedor, el número de factures que ha venut i el percentatge que suposa sobre el total. Podria ser que en el moment de calcular el percentatge, el número resultant s'haja de convertir a numèric per a que dóne bé el resultat, ja que en fer una operació amb enters, el resultat serà enter. Aleshores hauríem d'obligar a que el número tinga decimals (**::NUMERIC**). I la funció d'arrodonir és **ROUND**. Ordeneu pel nom.

![ref18]

**6.73** Traure tota la informació (amb l'import) de la factura més cara. Ha de ser per mig de subconsultes. Mireu que segurament hi haurà 2 subconsultes. En la més interna calculem l'import de les factures. En l'altra calculem el màxim. I en la consulta principal, busquem la factura que coincideix amb aquest màxim.

![ref19]

**6.74 (voluntari)** Obtenir el venedor que ha venut més unitats de cada categoria, sense considerar en la categoria el valor nul. Aquesta consulta la podríem considerar ja com molt avançada.

![ref20]

**6.75** Traure el nom de tots els clients i venedors implicats en alguna venda del primer trimestre de 2015. Intentar traure en una segona columna el text **Venedor** per als venedors, i **Client** per als clients. Ordenat pel nom.

![ref21]

**6.76a** Traure per mig de sentències d'operacions de conjunts els pobles on tenim algun venedor o algun client. No volem resultats repetits, i ho volem ordenat pel nom del poble.

![ref22]

Un total de **31 files**

**6.76b** Modificar l'anterior per a traure els pobles on tenim al mateix temps venedors i clients

![ref23]

**6.76c** Modificar l'anterior per a traure els pobles on tenim venedors però no tenim clients

![ref24]

[« Anterior](exercicis2.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis_de_tot_el_tema_amb_els_resultats.002.png
[ref2]: exercicis_de_tot_el_tema_amb_els_resultats.003.png
[ref3]: exercicis_de_tot_el_tema_amb_els_resultats.004.png
[ref4]: exercicis_de_tot_el_tema_amb_els_resultats.005.png
[ref5]: exercicis_de_tot_el_tema_amb_els_resultats.006.png
[ref6]: exercicis_de_tot_el_tema_amb_els_resultats.007.png
[ref7]: exercicis_de_tot_el_tema_amb_els_resultats.008.png
[ref8]: exercicis_de_tot_el_tema_amb_els_resultats.009.png
[ref9]: exercicis_de_tot_el_tema_amb_els_resultats.010.png
[ref10]: exercicis_de_tot_el_tema_amb_els_resultats.011.png
[ref11]: exercicis_de_tot_el_tema_amb_els_resultats.012.png
[ref12]: exercicis_de_tot_el_tema_amb_els_resultats.013.png
[ref13]: exercicis_de_tot_el_tema_amb_els_resultats.014.png
[ref14]: exercicis_de_tot_el_tema_amb_els_resultats.015.png
[ref15]: exercicis_de_tot_el_tema_amb_els_resultats.016.png
[ref16]: exercicis_de_tot_el_tema_amb_els_resultats.017.png
[ref17]: exercicis_de_tot_el_tema_amb_els_resultats.018.png
[ref18]: exercicis_de_tot_el_tema_amb_els_resultats.019.png
[ref19]: exercicis_de_tot_el_tema_amb_els_resultats.020.png
[ref20]: exercicis_de_tot_el_tema_amb_els_resultats.021.png
[ref21]: exercicis_de_tot_el_tema_amb_els_resultats.022.png
[ref22]: exercicis_de_tot_el_tema_amb_els_resultats.023.png
[ref23]: exercicis_de_tot_el_tema_amb_els_resultats.024.png
[ref24]: exercicis_de_tot_el_tema_amb_els_resultats.025.png
