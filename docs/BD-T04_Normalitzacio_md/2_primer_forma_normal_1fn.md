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

[« Anterior](1_introducci.md) | [Següent »](3_dependncia_funcional.md)
# <a name="main"></a>**2. Primer Forma Normal (1FN)**


|**Una taula està en 1FN si i només si els valors que componen cada atribut d'una tupla són atòmics. És a dir, en un atribut no han d'aparèixer valors repetitius.**|
| :- |

Per exemple, en la següent taula hi ha una sèrie de tipus de materials existents en una ferreteria. Un material té un codi que l'identifica, la seua descripció i les seues mides (la clau principal és el camp subratllat) 

**MATERIALS**

|**COD-MAT**|**DESCRIPCIÓ**|**MIDES**|
| :-: | :-: | :-: |
|039 |Cargol |3,5 - 5 - 7 - 9 |
|067 |Arandella |2 - 5 |
|461 |Broca |2,5 - 3 - 3,5 |

Els problemes que planteja són els següents: 

- La falta de espai en el camp per als valors que puguen aparèixer o, pel contrari el desaprofitament de l'atribut quan existeixen pocs valors. 
- La dificultat del tractament per a actualitzacions, consultes i recerques d'un valor determinat. 

Posar en 1FN 

Per a passar a 1FN una taula que no ho estava **es descompon** en **dues** distintes: 

**A)** La **primera taula** serà la projecció de la taula original sobre els següents atributs: 

- La clau de la taula original. 
- Els atributs atòmics (els que contenen valors únics). 

**MATERIALS**

|**COD-MAT**|**DESCRIPCIÓ**|
| :- | :- |
|039 |Cargol |
|067 |Arandella |
|461 |Broca |

**B)** La **segona taula** serà la projecció de la taula original sobre els següents atributs: 

- La clau de la taula original. 
- Els atributs que tenen valors múltiples, distribuint aquestos valors múltiples en tuples distintes i per tant en una fila existirà un únic valor elemental. 

La clau d'aquesta segona taula estarà formada per tots els atributs. 

**MAT-MIDES**

|**COD-MAT**|**MIDA**|
| :- | :- |
|039 |3,5 |
|039 |5 |
|039 |7 |
|039|9 |
|067 |2 |
|067 |5 |
|461 |2,5 |
|461 |3 |
|461 |3,5 |



**Nota**

També haurem de ser capaços de detectar que no està en 1FN quan tenim uns atributs multivaluats "encoberts". Per exemple, una variant de l'exemple anterior podria ser: 

**MATERIALS**

|**COD-MAT**|**DESCRIPCIÓ**|**MIDA1**|**MIDA2** |**MIDA3**|**MIDA4** |
| :-: | :-: | :-: | :- | :- | :- |
|039 |Cargol |3,5 |5|7|9|
|067 |Arandella |2 |5| | |
|461 |Broca |2,5 |3|3,5| |



Es veu que es tracta d'una manera de "dissimular" els atributs multivaluats. Estem davant del mateix cas que en l'exemple de dalt i tindrem els mateixos problemes, i per tant la solució és la mateixa.

[« Anterior](1_introducci.md) | [Següent »](3_dependncia_funcional.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
