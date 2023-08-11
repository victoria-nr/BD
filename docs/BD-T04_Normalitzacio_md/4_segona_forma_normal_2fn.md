Bases de Dades

- [Tema 4: Normalització](index.md)
- [Objectius](objectius.md)
- [1. Introducció](1_introducci.md)
- [2. Primer Forma Normal (1FN)](2_primer_forma_normal_1fn.md)
- [3. Dependència Funcional](3_dependncia_funcional.md)
- [4. Segona Forma Normal (2FN)](4_segona_forma_normal_2fn.md)
- [5. Dependència Funcional Transitiva](5_dependncia_funcional_transitiva.md)
- [6. Tercera Forma Normal (3FN)](6_tercera_forma_normal_3fn.md)
- [7. Forma Normal Boyce-Codd (FNBC)](7_forma_normal_boycecodd_fnbc.md)
- [Resum](resum.md)
- [Exercicis](exercicis.md)
- [Autoavaluació](autoavaluaci.md)

[« Anterior](3_dependncia_funcional.md) | [Següent »](5_dependncia_funcional_transitiva.md)
# <a name="main"></a>**4. Segona Forma Normal (2FN)**


|<p>**Una taula es diu que està en 2FN si i només si compleix dues condicions:**</p><p>- **Es troba en 1FN.**</p><p>- **Tot atribut secundari (aquells que no pertanyen a la clau principal, els que es troben fora de la caixa) depèn totalment (té una dependència funcional total) de la clau completa i, per tant, no d'una part d'ella.**</p>|
| :- |

Aquesta forma normal només es considera si la clau principal és composta, i per tant, està formada per diversos atributs. 

Si una taula **T** té com a atributs **A, B, C, D** i la clau és **A . B** complint-se les dependències: 

**A . B** → **C**

**B** → **D**

S'observa que la taula no es troba en 2FN ja que l'atribut D no té una dependència funcional total amb la clau completa A . B , sinó amb una part de la clau (B). El graf de les dependències funcionals seria:



![ref1]



**Si existeix una fletxa que ix de l'interior de la caixa que engloba la clau, aleshores la taula no està en 2FN.**



Posar en 2FN 

Per a convertir una taula que no està en segona forma normal a 2FN, es realitza una projecció i es crea: 

**A)** Una **primera taula** amb la clau i totes les seues dependències totals amb els atributs secundaris afectats: 

![ref2]

**B)** Una **segona taula** amb la part de la clau que té dependències, i els atributs secundaris implicats: 

![ref3]

La clau de la nova taula T2 serà l'antiga part de la clau. 



**Exemple**: Taula amb les persones que treballen en diverses empreses amb el sou corresponent, amb els atributs:**DNI , NOM , EMPRESA , SOU**

Entre els atributs existeixen les dependències: 

**DNI** → **NOM**

**DNI . EMPRESA** → **SOU**

El graf que mostra les dependències és el següent: 

![ref4]

És evident que la taula no es troba en 2FN, després de normalitzar s'obté: 

![ref5]

[« Anterior](3_dependncia_funcional.md) | [Següent »](5_dependncia_funcional_transitiva.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 4_segona_forma_normal_2fn.002.png
[ref2]: 4_segona_forma_normal_2fn.003.png
[ref3]: 4_segona_forma_normal_2fn.004.png
[ref4]: 4_segona_forma_normal_2fn.005.png
[ref5]: 4_segona_forma_normal_2fn.006.png
