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

[« Anterior](43_relacions_mn.md) | [Següent »](45_entitats_dbils.md)
# <a name="main"></a>**4.4 Relacions 1:1**


No hi ha una forma única de traduir aquestes relacions. Tres seran les possibles traduccions, segons la participació total o parcial de les entitats en la relació, i també segons el que ens diga el "*sentit comú*". 

- Si de les dues entitats que entren la relació, **A** i **B**,** una d'elles i només una, participa de forma total, per exemple **B**, traduirem la relació 1:1 com una **clau externa** en la taula corresponent a l'entitat que participa de forma total (**B**). Podem obligar també a que aquest camp que serà clau externa siga **no nul** (ja que totes les ocurrències de **B** entren en la relació). També podem fer que aquest camp siga **únic** (no es podrà repetir, ja que si es puguera repetir seria una relació 1:N). A més, inclourem en **B** tots els possibles atributs de la relació. 

Per exemple, la relació ***dirigeix***, que és 1:1 entre **EMPLEAT** i **DEPARTAMENT**: 

![ref1] 

Com que l'entitat de la dreta participa de forma total, triarem **DEPARTAMENT**: 

![ref2] 

Ho fem d'aquesta manera perquè tots els departaments tenen director, però no tots els empleats són directors. Si posàrem la clau externa en la taula **EMPLEAT** (s'anomenaria per exemple **dep\_que\_dirigeix**) moltes vegades estaria buit, ja que relativament són pocs els empleats que dirigeixen un departament. 

Vegem un altre exemple de relació 1:1, el de les papallones. Teníem una relació 1:1 entre **PERSONA** i **COL·LECCIÓ**

![ref3] 

Triaríem **COL·LECCIÓ**, ja que entra de forma plena o total en la relació. 

![ref4] 

- Si les dues entitats participen de forma total, es pot considerar tot (les dues entitats i la relació, amb els seus possibles atributs) com una sola taula. En la pràctica això serà prou estrany, perquè ja ho hauríem considerat una sola entitat. Per exemple, considerem que totes les persones que estudiem tenen una col·lecció: 

![ref5] 

Aleshores podríem considerar una única taula, que continga les dades de la persona i de la seua col·lecció: 

![ref6] 

De tota manera, pot ser ens interesse (per separar clarament els dos tipus d'informació) dues taules. Aleshores podríem traduir-lo com en el primer punt, amb una clau externa (no nula) en una de les dues taules, i hauríem de triar la taula que *menys* s'utilitze. 

- Si les dues entitats participen de forma parcial, com que si posem una clau externa en una de les dues, moltes vegades tindrà valor nul, podem traduir-la com una nova taula que marque la relació, on hi haurà una tupla per cada relació entre dues ocurrències. Inclouríem en la nova taula els possibles atributs de la relació. 

En l'exemple podria ser que les col·leccions pertanyen a una persona particular o a una institució (no tenen propietari): 

![ref7]

Quedaria: 

![ref8]

Però com comentàvem al principi, haurem d'aplicar el sentit comú, ja que potser una de les dues podria participar de forma "quasi" total (per exemple, quasi totes les col·leccions són d'una persona). Aleshores podria ser millor traduir-lo com en el primer cas, posant la clau externa en la que participa de forma "quasi" total, ja que aquesta tindrà relativament pocs valors nuls, i seria més costós mantenir una altra taula. Evidentment la clau externa sí que podria ser nula, en aquest cas. 



Resumint, **una relació 1:1 quasi sempre la traduirem com una clau externa en la taula que participa en la relació de forma total o quasi total** (o la que previsiblement té més ocurrències en la relació) 

[« Anterior](43_relacions_mn.md) | [Següent »](45_entitats_dbils.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 44_relacions_11.002.png
[ref2]: 44_relacions_11.003.png
[ref3]: 44_relacions_11.004.png
[ref4]: 44_relacions_11.005.png
[ref5]: 44_relacions_11.006.png
[ref6]: 44_relacions_11.007.png
[ref7]: 44_relacions_11.008.png
[ref8]: 44_relacions_11.009.png
