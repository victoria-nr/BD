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

[« Anterior](62_entitats_dbils.md) | [Següent »](aplicaci_a_lexemple5.md)
# <a name="main"></a>**6.3 Generalització i herència**


Anem a comentar, prou per damunt, un altre aspecte recollit en el Model E/R Estès. I és quan una entitat es pot subdividir en d'altres. Per exemple podríem refinar l'entitat EMPLEAT en CAPS, SECRETARIS i TREBALLADORS. 

Empleat seria el **SUPERTIPUS** o **SUPERCLASSE** i els altres els **SUBTIPUS**. EMPLEAT seria la **GENERALITZACIÓ** dels altres. I els altres serien l'**ESPECIALITZACIÓ** d'EMPLEAT. 



![](63_generalitzaci_i_herncia.002.png)



Un aspecte important és l'**HERÈNCIA**, que consisteix en què els subtipus heretaran els atributs del supertipus, de manera que no caldrà repetir-los. Únicament s'hauran de declarar els atributs específics de la subclasse (en CAP podríem tenir l'opinió del seu departament; en SECRETARI número de pulsacions per segon o coneixements d'informàtica; en TREBALLADOR si està disposat a fer hores extres). 

Hi ha més d'una classe d'especialització depenent de dos criteris: 

- Si se **solapen** (una ocurrència de la superclasse pot pertànyer a més d'una subclasse) o són **disjuntes** (una ocurrència de la superclasse només pot pertànyer a una subclasse). Per exemple els empleats especialitzats per torn de treball (matí, vesprada, nit), pot donar-se el cas que algun treballador treballe matí i vesprada de forma no intensiva (atenció a públic), i per tant seria solapada. Un exemple d'especialització no solapada seria l'especialització per tipus de treball (cap, secretari, treballador), on un empleat no pot pertànyer a dues subclasses.

- Si és **total** (totes les ocurrències del supertipus pertanyen a algun subtipus) o **parcial**. Un exemple de total seria una especialització per dedicació a l'empresa (completa o no completa). Un exemple de parcial seria l'especialització per tipus de treball (cap, secretari, treballador) ja que podria haver algun treballador que no coincidesca (un assessor,...) 

No anem a insistir molt en aquest tema perquè a més, en el tractament posterior (quan passem al Model Relacional), de vegades es representen totes les entitats, però de vegades per motius pràctics se simplifica (suprimint bé el supertipus, bé els subtipus). 

[« Anterior](62_entitats_dbils.md) | [Següent »](aplicaci_a_lexemple5.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
