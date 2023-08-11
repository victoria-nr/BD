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

[« Anterior](4_segona_forma_normal_2fn.md) | [Següent »](6_tercera_forma_normal_3fn.md)
# <a name="main"></a>**5. Dependència Funcional Transitiva**




La dependència funcional transitiva s'aplica per a analitzar les taules en tercera forma normal (3FN). Consisteix bàsicament a considerar que **un atribut no primari només ha de conèixer-se a través de la clau principal o claus secundàries**. En un altre cas, estarà produint redundància d'informació amb les anomalies típiques que porta amb ella. 

|<p>Suposem tres subconjunts distints d'atributs A , B i C que pertanyen a una taula T, de manera que es compleixen les condicions: </p><p>**A** → **B** i **B** −∕→ **A**</p><p>Es diu que C té una **dependència funcional transitiva** amb A o que és transitivament dependent de A si es compleix que **B** → **C**</p>|
| :- |

Gràficament es pot mostrar: 

![ref1]

Per tant, un atribut C és transitivament dependent d'un altre A si es coneix per diferents vies, una directament, i una altra a partir d'un altre atribut intermedi B. 

Per exemple, considerem tres atributs que formen part de la taula ALUMNES: 

NUMMAT = núm. de matrícula. 

GRUP = Grup assignat. 

AULAGRUP = Aula assignada al grup. 



**NUMMAT** → **GRUP | AULAGRUP**

**GRUP** → **AULAGRUP**


L'atribut AULAGRUP és transitivament dependent de NUMMAT, ja que es pot conèixer per mig de l'atribut NUMMAT i a través de l'atribut GRUP 



![ref2]



[« Anterior](4_segona_forma_normal_2fn.md) | [Següent »](6_tercera_forma_normal_3fn.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 5_dependncia_funcional_transitiva.002.png
[ref2]: 5_dependncia_funcional_transitiva.003.png
