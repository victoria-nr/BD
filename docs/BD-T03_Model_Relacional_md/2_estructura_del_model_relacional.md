Bases de Dades

- [Tema 3: Model Relacional](index.md)
- [Objectius i coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. Estructura del Model Relacional](2_estructura_del_model_relacional.md)
- [3. Restriccions](3_restriccions.md) 
  - [3.1 Restriccions inherents](31_restriccions_inherents.md)
  - [3.2 Restriccions d'usuari](32_restriccions_dusuari.md) 
    - [3.2.1 Restricció de domini](321_restricci_de_domini.md)
    - [3.2.2 Restricció de clau principal](322_restricci_de_clau_principal.md)
    - [3.2.3 Restricció d'unicitat](323_restricci_dunicitat.md)
    - [3.2.4 Restricció de valor no nul](324_restricci_de_valor_no_nul.md)
    - [3.2.5 Integritat referencial](325_integritat_referencial.md)
    - [3.2.6 Restriccions externes](326_restriccions_externes.md)
- [4. Tranformació del M. E/R al M. Relacional](4_tranformaci_del_m_er_al_m_relacional.md) 
  - [4.1 Entitats](41_entitats.md)
  - [4.2 Relacions 1:N](42_relacions_1n.md)
  - [4.3 Relacions M:N](43_relacions_mn.md)
  - [4.4 Relacions 1:1](44_relacions_11.md)
  - [4.5 Entitats dèbils](45_entitats_dbils.md)
  - [4.6 Resum dependències](46_resum_dependncies.md)
  - [4.7 Relacions ternàries](47_relacions_ternries.md)
  - [4.8 Especialitzacions](48_especialitzacions.md)
  - [4.9 Restriccions externes](49_restriccions_externes.md)
  - [4.10 Exemple](410_exemple.md)
- [5. Llenguatges relacionals](5_llenguatges_relacionals.md)
- [6. Exercicis](6_exercicis.md)
- [Auto-avaluació](autoavaluaci.md)

[« Anterior](1_introducci.md) | [Següent »](3_restriccions.md)
# <a name="main"></a>**2. Estructura del Model Relacional**


L'element bàsic del Model Relacional és la **RELACIÓ**, que serà una taula o matriu bidimensional amb unes característiques o restriccions que comentarem més avant.

![ref1]





Normalment una relació té un **NOM** (p.e. **Empleat**) encara que ocasionalment no en tindrà, per exemple una taula que siga el resultat d'una consulta poc freqüent.



Les **FILES**, on tenim la informació de les ocurrències, dels individus, també s'anomenen **TUPLES** (de vegades per similitud amb fitxers també s'anomenen **REGISTRES**).



Les **COLUMNES**, que seran característiques que ens interessen dels individus i que en cada tupla agafa un valor, les anomenarem també **ATRIBUTS** (o **CAMPS**).



El conjunt de valors possibles que pot agafar un atribut determinat s'anomena **DOMINI**. Més avant veurem que els dominis s'intentaran definir el millor possible, per prevenir errors.



L'**ESQUEMA o ESTRUCTURA DE LA RELACIÓ** és la definició de la relació, és a dir, atributs que té, dominis d'aquestos i restriccions que podrem definir, que veurem en la següent pregunta.



L'**ESTAT DE LA RELACIÓ** és la informació que conté en un determinat moment. Normalment l'estat variarà contínuament al llarg del temps, bé perquè s'afegeixen noves tuples (augmenta la cardinalitat), bé perquè es modifica el valor d'algun atribut en alguna tupla. En canvi l'esquema difícilment canviarà.



Una **CLAU CANDIDATA** és un atribut o conjunt d'atributs que identifiquen unívocament cada tupla de la relació. En l'exemple podrien ser claus candidates **Dni**, **Nom**, fins i tot ens podríem plantejar combinacions, com el conjunt **(Nom, Data\_n)**, ja que sembla impossible que dues persones de l'empresa es diguen igual i damunt hagen nascut el mateix dia. De entre totes les claus candidates en triarem una, que serà la **CLAU PRINCIPAL** o **CLAU PRIMÀRIA**, i servirà per a identificar de forma efectiva en el Model cadascuna de les tuples.



Podria donar-se el cas que un atribut no agafe cap valor per a una tupla determinada, per exemple, un empleat que no tinga telèfon. Aleshores li donarem el **VALOR NUL**.



Per últim, les relacions o taules poden ser **PERMANENTS** o **TEMPORALS**. Les primeres es guarden. Les segones, normalment resultat d'una consulta ocasional, no.



Representarem la taula amb el nom de la taula en majúscules seguit, entre parèntesis, en minúscules i separats per comes, pels noms dels camps, amb la clau principal subratllada. També és convenient fugir dels caràcters especials (vocals accentuades, ç, ñ, guionet, ...) per no tenir problemes quan anem a implementar-la en un SGBD determinat (Access, Oracle, PostgreSQL, ...). Per a una millor lectura intentarem posar sempre la clau principal al principi, el o els primers camps.

EMPLEAT (dni, nom, adreca, telefon, sou, data\_n)

També podem utilitzar una forma alternativa de representar-la, amb un requadre que agafa tota la taula, dalt el nom de la taula, i baix cadascun dels camps, posant la clau principal en negreta o subratllada.

![ref2]



[« Anterior](1_introducci.md) | [Següent »](3_restriccions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 2_estructura_del_model_relacional.002.png
[ref2]: 2_estructura_del_model_relacional.003.png
