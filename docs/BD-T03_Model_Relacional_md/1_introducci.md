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

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_estructura_del_model_relacional.md)
# <a name="main"></a>**1. Introducció**


En 1970 **E.F. Codd** va introduir la teoria matemàtica de les relacions en el camp dels SGBD. El model de dades que va crear s'anomena **MODEL RELACIONAL**, amb una base matemàtica (la de les relacions) molt sòlida, on les dades s'estructuren en forma de relacions (taules) que són estructures de dades simples i uniformes, que permeten una fàcil comprensió. 

En el moment en què va sorgir, els models que funcionaven eren el jeràrquic i el de xarxa (també anomenat Codasyl, pel grup de treball que va estandaritzar-lo). Com a model els va superar perquè, com va dir el mateix Codd, "*proporciona un mitjà per a descriure les dades amb la seua estructura únicament, sense haver de superposar cap estructura addicional per a representar-se en la màquina"* (és a dir, sense punters ni històries). 

A pesar d'això va estar uns anys en competència amb aquells, amb molta gent molt reticent, ja que els productes comercials que eixien no eren suficientment eficients, potser perquè la tecnologia de l'època no ho permetia. A partir dels anys 80, quan la tecnologia ho va permetre, van eixir productes millors, com per exemple l'**ORACLE** (1979), i aleshores la seua implantació va ser aplastant. 

Els objectius del Model Relacional són: 

- **Fidelitat**, per a originar esquemes que representen fidelment la informació (els objectes i relacions entre ells) que existeix en el domini del problema.

- **Independència física**[1][^1], per a que la manera de guardar les dades no influesca en la seua manipulació lògica, i així els usuaris que accedeixen a aquestes dades no hagen de modificar els seus programes per canvis en l'emmagatzematge físic.

- **Independència lògica**, per a que les vistes externes no es vegen afectades per canvis en l'esquema conceptual de la B.D.

- **Flexibilitat**, per a poder oferir les dades a cada usuari de la forma més adequada a la seua aplicació.

- **Uniformitat**, les estructures lògiques de les dades presenten un aspecte simple i uniforme (les taules), cosa que facilita la concepció i manipulació per part dels usuaris.

- **Senzillesa**, les característiques anteriors, unides a uns llenguatges d'usuari senzills, fan que el M. Relacional siga fàcil d'entendre i d'utilitzar per l'usuari final.

Recordeu que les **relacions** del Model Relacional són les **taules**. No són el mateix que les relacions del Model Entitat-Relació. Per evitar confusions intentarem anomenar-les sempre taules. -----

<a name="_ftn1"></a>[\[1\]](../SGBD-T03%282008%29Model%20Relacional/#_ftnref1 "_ftn1") En realitat tant la independència física com lògica les han intentades aconseguir tots els models. 

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_estructura_del_model_relacional.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[^1]: 