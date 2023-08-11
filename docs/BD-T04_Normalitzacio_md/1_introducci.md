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

[« Anterior](objectius.md) | [Següent »](2_primer_forma_normal_1fn.md)
# <a name="main"></a>**1. Introducció**


El procés de normalització s'encarrega de seguir una sèrie de passos o normes. Després d'aplicar-les totes, s'obtenen les dades agrupades en diferents taules, de manera que és l'estructura òptima per a la seua implementació, gestió i explotació des de diferents aplicacions futures. 

La normalització es basa en que les dades han de ser independents de les aplicacions que les utilitzen, i per tant no seran optimitzades per a una aplicació determinada sinó que seran optimitzades, en general, per a qualsevol aplicació futura. El seu objectiu és obtenir el **major nombre de taules possibles**. Cadascuna d'aquestes taules estarà formada pels atributs imprescindibles per a representar l'entitat o la relació entre entitats. 



Avantatges que s'obtenen després de la normalització: 

- **Facilitat d'ús.** Les dades estan agrupades en taules que identifiquen clarament una entitat o una relació.

- **Flexibilitat.** La informació que necessiten els usuaris es pot obtenir de les taules relacionals per mig de les operacions de l'àlgebra relacional. No es tenen unes estructures rígides de dades sinó que es poden combinar de manera que s'obtinguen múltiples vistes.

- **Facilitat de Implementació.** Les taules resultants són simples.

- **Claredat.** La representació de la informació és clara i senzilla per a l'usuari. Són taules senzilles.

- **Redundància mínima.** La informació no estarà duplicada innecessàriament dins de les estructures.

- **Màxim rendiment de les aplicacions.** Només es tracta aquella informació que serà d'utilitat a cada aplicació.

Dins de tot el procés de creació d'una Bases de Dades, la normalització es faria després de construir tot l'esquema relacional, és a dir, primer es construiria l'esquema amb el Model E/R, després es traduiria al Model Relacional, i posteriorment es normalitzarien aquestes taules de l'esquema relacional. La veritat, però, és que normalment les taules que ens eixiran en l'esquema relacional estaran prou normalitzades, encara que pot ser molt convenient analitzar totes les taules. 

**La vertadera utililitat i necessitat de la normalització està en la conversió o actualització de sistemes d'informació antics**. Així, si volem actualitzar una aplicació basada en fitxers tradicionals, la normalització de les taules serà absolutament necessària. 

[« Anterior](objectius.md) | [Següent »](2_primer_forma_normal_1fn.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
