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

[« Anterior](42_relacions_1n.md) | [Següent »](44_relacions_11.md)
# <a name="main"></a>**4.3 Relacions M:N**


Per cada relació **M:N** construirem una **nova taula** on s'inclouran com a clau externa les claus principals de les dues entitats, i a més la seua combinació constituirà (o formarà part de) la clau principal. Inclourem també els possibles atributs de la relació.

En l'exemple:



![ref1]

Cada vegada que ens trobem amb una relació M:N i la traduïm per una nova taula haurem de **preguntar-nos si és suficient amb la clau principal** formada per les dues claus externes, o si fa falta afegir un altre camp. Hem de ser conscients que la clau principal no puga repetir-se, que hi haja 2 files amb la mateixa clau principal. Així, en l'exemple, ens hauríem de fer la següent pregunta: pot un empleat treballar en el mateix projecte més d'una vegada? En aquest cas la contestació és negativa, i per tant és suficient amb aquesta clau principal.

Però suposem que la resposta és que sí que pot treballar més d'una vegada al llarg del temps. En aquest cas seria una espècie d'històric, on faria falta, a més, saber quan comença i quan acaba de treballar en un projecte un determinat treballador (serien atributs de la relació):

![ref2]


Aleshores, com no és suficient amb la clau principal formada per les dues claus externes, inclourem un altre camp en la clau principal. Sembla que el més adequat seria **Data\_c** (ja no es pot donar el cas que el mateix treballador treballe més d'una vegada en el mateix projecte, començant el mateix dia)

![ref3]

Però per una altra banda, les claus principals molt llargues no són operatives, i encara que la traducció literal siga com hem dit, per motius pràctics podem canviar la clau principal. Considerarem que el nombre màxim de camps en la clau principal és de 3. 4 ja són massa, i aleshores buscarem una altra clau principal (un codi de treball, per exemple). Les claus externes continuarien sent-ho.

[« Anterior](42_relacions_1n.md) | [Següent »](44_relacions_11.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 43_relacions_mn.002.png
[ref2]: 43_relacions_mn.003.png
[ref3]: 43_relacions_mn.004.png
