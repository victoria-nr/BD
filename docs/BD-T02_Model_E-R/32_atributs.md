Bases de Dades

- [Tema 2: MODEL ENTITAT-RELACIÓ](index.md)
- [Objectius i coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. Exemple](2_exemple.md)
- [3. Les Entitats del Model E/R](3_les_entitats_del_model_er.md) 
  - [3.1 Entitats](31_entitats.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple.md)
  - [3.2 Atributs](32_atributs.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple0.md)
  - [3.3 Dominis](33_dominis.md)
- [Exercicis](exercicis.md)
- [4. Les Relacions del Model E/R](4_les_relacions_del_model_er.md) 
  - [4.1 Relació](41_relaci.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple1.md)
  - [4.2 Atributs de Relació](42_atributs_de_relaci.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple2.md)
  - [4.3 Tipus de Relació o Cardinalitat](43_tipus_de_relaci_o_cardinalitat.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple3.md)
- [Exercicis](exercicis0.md)
- [5. Relacions de grau major que dos](5_relacions_de_grau_major_que_dos.md)
- [6. Model E/R Estès](6_model_er_ests.md) 
  - [6.1 Cardinalitat màxima i mínima. Participació total.](61_cardinalitat_mxima_i_mnima_participaci_total.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple4.md)
  - [6.2 Entitats dèbils](62_entitats_dbils.md)
  - [6.3 Generalització i herència](63_generalitzaci_i_herncia.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple5.md)
- [7. Restriccions externes](7_restriccions_externes.md)
- [Exercicis](exercicis1.md)
- [Informació addicional](informaci_addicional.md)
- [Auto-avaluació](autoavaluaci.md)

[« Anterior](aplicaci_a_lexemple.md) | [Següent »](aplicaci_a_lexemple0.md)
# <a name="main"></a>**3.2 Atributs**


Un **ATRIBUT** és cadascuna de les característiques d'una entitat que ens interessen. 

Per exemple en l'entitat EMPLEAT tindrem els atributs *nom, DNI, adreça, telèfon, sou* i *data de naixement*. 

No considerarem atributs les característiques que no ens interessen (estatura, talla pantalons, etc.) 

Una ocurrència d'entitat tindrà un **VALOR** per a cada atribut, per exemple *Joan Peris, 18.901.234, 964-22.33.44, 1.200,00€., 12-5-1960.*

Però de vegades potser que el contingut d'un atribut siga el valor **NUL** (per exemple si no té telèfon o el desconeixem). 

Els atributs poden ser **SIMPLES** o **COMPOSTOS**, si estan formats per una única informació o per més d'una. Així, un exemple d'atribut compost seria el nom que podria estar format per: *nom=(nom de pila, primer cognom, segon cognom)*. 

Poden haver atributs **MULTIVALUATS**, que vol dir que poden agafar més d'un valor. Per exemple suposem que en el cas anterior considerem el camp *altres telèfons*** (per si en l'empresa hi ha moments que hem de localitzar l'empleat urgentment). Potser un empleat no tinga cap valor en aquest camp. I potser un altre en tinga dos (el mòbil i el d'una segona residència). En general fugirem d'aquestos camps per comoditat, però el model ho accepta. 

També poden haver atributs **DERIVATS**, és a dir, atributs que es poden calcular a partir d'altres. Podria ser el cas del camp *edat*, que es pot calcular a partir de la data del sistema i de *data de naixement*. 



El model necessita poder identificar cada ocurrència sense marge d'error. Hi haurà algun atribut (o conjunt d'atributs) que acomplirà aquesta premisa d'identificar unívocament. I per a que això siga possible, aquest atribut haurà de tenir valors distints per a totes les ocurrències (sinó no podria identificar-les); i al mateix temps no podrà tenir en cap cas el valor nul. En l'exemple EMPLEAT, el *nom* o el *DNI* servirien per identificar. En canvi el sou no serviria, ja que més d'un empleat pot tenir el mateix sou. El telèfon tampoc, perquè potser siga nul. 

Als atributs (o conjunts d'atributs) que acompleixen la condició anterior els anomenarem **CLAUS CANDIDATES**, i d'entre totes les claus candidates triarem una i l'anomenarem **CLAU PRINCIPAL**. 

Totes les entitats han de tenir una clau principal. És una de les restriccions del Model E/R. 



Representarem els atributs amb un cercle unit a l'entitat per una línia, i en l'interior o al costat posarem el nom de l'atribut. La clau principal l'assenyalarem subratllant-la, o amb el cercle negre. 

Per als atributs multivaluats posarem ***n*** en la línia. I els derivats els representarem amb línies discontínues. 

Ací tindríem dues maneres (absolutament equivalents) de representar l'entitat EMPLEAT amb els seus atributs.

|![ref1]| |![ref2]|
| :- | :- | :- |

[« Anterior](aplicaci_a_lexemple.md) | [Següent »](aplicaci_a_lexemple0.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 32_atributs.002.png
[ref2]: 32_atributs.003.png
