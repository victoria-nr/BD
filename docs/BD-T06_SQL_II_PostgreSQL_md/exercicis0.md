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

[« Anterior](223_combinaci_externa.md) | [Següent »](23_subconsultes.md)
# <a name="main"></a>**Exercicis**
![](exercicis0.002.png)
## **Exercicis Apartat 2.2.3**
**6.60** Traure el codi i el nom dels clients que no tenen cap factura.

**6.61** Traure el codi, descripció i total d'unitats venudes de tots els articles, fins i tot d'aquells que no s'ha venut res.

**Nota**

Per a deixar-lo més bonic, com que la suma de valors nuls no és 0 sinó nul, per a que ens aparegue el valor 0 podem utilitzar la funció COALESCE(*valor*,0), que si el valor és nul torna un 0.

**6.62** Traure el nom de tots els pobles i el número de clients en cas de que en tinguen. Ordena per número de clients de forma descendent.

**6.63** Traure el codi i la descripció de les categories, amb el número d'articles de cada categoria i el número total d'unitats venudes de cada categoria, d'aquelles categories de les quals tenim més de 15 articles, i ordenat per número d'articles de forma descendent. Aquesta sentència ja és prou complicada. Concretament haureu de tenir en compte que:

- Voldrem traure el número d'articles de cada categoria, però potser alguns articles no s'han venut, i per tant no apareixeran en la taula LINIA\_FAC.
- I també tenim el problema que, com ens fa falta la taula LINIA\_FAC, un article venut en més d'una factura apareixerà més d'una vegada. Si comptem de forma normal, el comptaríem més d'una vegada cada article. Per tant voldrem comptar els diferents articles de cada categoria.

[« Anterior](223_combinaci_externa.md) | [Següent »](23_subconsultes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
