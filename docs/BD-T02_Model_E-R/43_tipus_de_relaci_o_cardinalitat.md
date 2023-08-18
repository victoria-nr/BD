Bases de Dades


Encara no hem reflectit tota la realitat. Per exemple no hem pogut expressar que un empleat pertany únicament a un departament, i en canvi pot estar en més d’un projecte. 

Això ho farem per mig de la cardinalitat, que ens durà a distintes classes de relacions. 

La **CARDINALITAT** especifica el número d'ocurrències d'una entitat que poden intervenir en la relació per cada ocurrència de l'altra entitat. 

Una ocurrència d'EMPLEAT (un empleat concret) només pot estar relacionat amb una ocurrència de DEPARTAMENT (Joan Peris pertany a Comptabilitat, i a cap altre departament més). En canvi una ocurrència de DEPARTAMENT pot estar relacionada amb moltes ocurrències d'EMPLEAT (tots els que hi pertanyen). Aleshores la relació PERTANY entre DEPARTAMENT i EMPLEAT té raó de cardinalitat **1:N** (un departament relacionat amb molts empleats, però un empleat amb un departament). 

Ho representarem així: 



![ref1]



o millor: 



![ref2]



Els distints tipus de relacions que hi pot haver són: 

- **1:1** (llegirem: **ú a ú**) com a màxim una ocurrència de cada. Per exemple la relació DIRIGEIX (un empleat dirigeix com a molt un departament, i un departament és dirigit per un empleat).
- **1:N** (llegirem: **ú a ena** o **ú a molts**) en una entitat una ocurrència i en l'altra moltes.
- **M:N** (llegirem: **ema a ena** o **molts a molts**) hi ha més d'una ocurrència en cada entitat. Per exemple la relació TREBALLA (un empleat pot treballar en més d'un projecte, i en un projecte pot treballar més d'un empleat).



Per a poder distingir aquesta cardinalitat ens farem dues preguntes, resultat de fixar una ocurrència en una entitat i veure quantes ocurrències es relacionen en l'altra entitat. És a dir, per a una ocurrència d'una, quantes hi ha de l'altra. En l'exemple de més amunt: 

- A un departament determinat, quants empleats poden pertànyer? (molts).
- Un empleat determinat, a quants departaments pot pertànyer? (a un).

Aquestes preguntes normalment tenen molt fàcil contestació. Si hi ha dubte hauríem d'investigar millor en les especificacions. 

**Nota**

La cardinalitat M:N també la podríem representar N:N. Senzillament vol dir que són moltes ocurrències de cada entitat per cadascuna de l'altra. En aquestos apunts normalment posaré M:N, senzillament perquè "sóna" millor. 

[« Anterior](aplicaci_a_lexemple2.md) | [Següent »](aplicaci_a_lexemple3.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 43_tipus_de_relaci_o_cardinalitat.002.png
[ref2]: 43_tipus_de_relaci_o_cardinalitat.003.png
