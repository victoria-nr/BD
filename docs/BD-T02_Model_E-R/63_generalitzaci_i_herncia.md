Bases de Dades


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
