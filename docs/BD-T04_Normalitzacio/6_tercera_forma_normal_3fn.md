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

[« Anterior](5_dependncia_funcional_transitiva.md) | [Següent »](7_forma_normal_boycecodd_fnbc.md)
# <a name="main"></a>**6. Tercera Forma Normal (3FN)**


|<p>**Una taula es diu que està en 3FN si i només si es compleixen dues condicions:**</p><p>- **Es troba en 2FN.**</p><p>- **No existeixen atributs no primaris (atributs que no formen part de la clau principal) que són transitivament dependents de cada clau candidata de la taula.**</p>|
| :- |

Açò vol dir que un atribut secundari només es pot conèixer a través de la clau principal o claus candidates de la taula i no per mig d'un altre atribut no primari. 

En el graf de dependències només han de mostrar-se les dependències transitives i no aquelles dependències funcionals a partir de les claus candidates, perquè se sap que per ser claus ja coneixen tots els atributs. 



Exemple: A és la clau principal, B és una clau candidata i es donen les següents dependències: 

**A** → **B B** → **A C** → **D**

**A** → **C B** → **C C** → **E**

**A** → **D B** → **D**

**A** → **E B** → **E**

El graf queda del següent mode:

|![ref1] |O bé |![ref2]|
| :- | :- | :- |



Les fletxes que mostren les dependències funcionals que té la clau candidata B no es representen (com hem dit anteriorment) perquè són evidents i no simplifiquen la visió del graf. A més a més, per a la normalització, no es necessiten per a res; pel contrari, solen complicar l'anàlisi. 

La taula T no està en 3FN ja que els atributs D i E són transitivament dependents respecte de la clau A. 



Posar en 3FN 

Per a normalitzar una taula que no estiga en tercera forma normal, és a dir, que tinga dependències transitives, descompondrem la taula en més d'una taula: 

**A)** Una **primera taula** amb la clau principal més els atributs que no depenen transitivament 

![ref3]

**B)** Una **segona taula** amb els atributs que depenen transitivament, més l'atribut de qui depenen, que serà clau principal 

![ref4]

Es farà una descomposició per cada dependència transitiva que hi haja que afecte a camps distints. 



Per a l'exemple dels atributs NUMMAT, GRUP i AULAGRUP tenim el següent graf: 

![ref5] 

Una vegada descomposta la taula en dos segons l'algoritme anterior, tindrem dues taules 

![ref6]

Les dues taules resultants sí que es troben en 3FN. 

[« Anterior](5_dependncia_funcional_transitiva.md) | [Següent »](7_forma_normal_boycecodd_fnbc.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 6_tercera_forma_normal_3fn.002.png
[ref2]: 6_tercera_forma_normal_3fn.003.png
[ref3]: 6_tercera_forma_normal_3fn.004.png
[ref4]: 6_tercera_forma_normal_3fn.005.png
[ref5]: 6_tercera_forma_normal_3fn.006.png
[ref6]: 6_tercera_forma_normal_3fn.007.png
