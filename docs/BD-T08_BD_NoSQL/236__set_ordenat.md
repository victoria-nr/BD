Bases de Dades

- [Tema 8: Bases de Dades NoSQL](index.md)
- [1 - Introducció](1__introducci.md)
- [2 - BD Clau-Valor: Redis](2__bd_clauvalor_redis.md) 
  - [2.1 - Instal·lació de Redis](21__installaci_de_redis.md)
  - [2.2 - Entron gràfic: Redis Desktop Manager](22__entron_grfic_redis_desktop_manager.md)
  - [2.3 - Utilització de Redis](23__utilitzaci_de_redis.md) 
    - [2.3.1 - Strings](231__strings.md)
    - [2.3.2 - Keys](232__keys.md)
    - [2.3.3 - Hash](233__hash.md)
    - [2.3.4 - List](234__list.md)
    - [2.3.5 - Set](235__set.md)
    - [2.3.6 - Set ordenat](236__set_ordenat.md)
- [3 - MongoDB](3__mongodb.md) 
  - [3.1 - Estructura JSON](31__estructura_json.md)
  - [3.2 - Instal·lació de MongoDB](32__installaci_de_mongodb.md) 
    - [3.2.1 - Connexió al servidor de l'Institut](321__connexi_al_servidor_de_linstitut.md)
  - [3.3 - Utilització de MongoDB](33__utilitzaci_de_mongodb.md) 
    - [3.3.1 - Tipus de dades](331__tipus_de_dades.md)
    - [3.3.2 - Operacions bàsiques](332__operacions_bsiques.md)
    - [3.2.3 - Operacions d'actualització avançada](323__operacions_dactualitzaci_avanada.md) 
      - [3.3.3.1 - $set](3331__set.md)
      - [3.3.3.2 - $unset](3332__unset.md)
      - [3.3.3.3 - $rename](3333__rename.md)
      - [3.3.3.4 - $inc](3334__inc.md)
      - [3.3.3.5 - Elements d'un array](3335__elements_dun_array.md)
      - [3.3.3.6 - Inserció en Arrays: $push](3336__inserci_en_arrays_push.md)
      - [3.3.3.7 - Eliminació en arrays: $pop i $pull](3337__eliminaci_en_arrays_pop_i_pull.md)
      - [3.3.3.8 - Upsert](3338__upsert.md)
  - [3.4 - Consulta de documents](34__consulta_de_documents.md) 
    - [3.4.1 - Paràmetres de les funcions find() i findOne()](341__parmetres_de_les_funcions_find_i_findone.md)
    - [3.4.2 - Operadors de les condicions](342__operadors_de_les_condicions.md)
    - [3.4.3 - Agregació](343__agregaci.md)
- [4 - BD XML: eXist-db](4__bd_xml_existdb.md) 
  - [4.1 - Instal·lació d'eXist-db](41__installaci_dexistdb.md)
  - [4.2 - Llenguatges de consultes XPATH i XQUERY](42__llenguatges_de_consultes_xpath_i_xquery.md) 
    - [4.2.1 - XPATH](421__xpath.md) 
      - [4.2.1.1 - Vista d'arbre](4211__vista_darbre.md)
      - [4.2.1.2 - Navegació](4212__navegaci.md)
      - [4.2.1.3 - Seqüències](4213__seqncies.md)
      - [4.2.1.4 - Funcions](4214__funcions.md)
    - [4.2.2 - XQUERY](422__xquery.md) 
      - [4.2.2.1 - Consultes XQuery](4221__consultes_xquery.md)
      - [4.2.2.2 - Variables](4222__variables.md)
      - [4.2.2.3 - Expressions avaluables](4223__expressions_avaluables.md)
      - [4.2.2.4 - Expressions FLWOR](4224__expressions_flwor.md)
      - [4.2.2.5 - Alternatives](4225__alternatives.md)
      - [4.2.2.6 - Exemple de consulta "elaborada"](4226__exemple_de_consulta_elaborada.md)
      - [4.2.2.7 - Funcions de eXist-db de manipulació de BD](4227__funcions_de_existdb_de_manipulaci_de_bd.md)
- [5 - FIREBASE (voluntari)](5__firebase_voluntari.md) 
  - [5.1 - Creació d'una aplicació](51__creaci_duna_aplicaci.md)
  - [5.2 - Realtime Database (RD)](52__realtime_database_rd.md)
  - [5.3 - Cloud Firestore (CF)](53__cloud_firestore_cf.md)
  - [5.4 - Cloud Storage](54__cloud_storage.md)
- [Exercicis](exercicis.md)

[« Anterior](235__set.md) | [Següent »](3__mongodb.md)
# <a name="main"></a>**2.3.6 - Set ordenat**
Els **Sets Ordenats** (**Sorted Set**) de **Redis** són Sets que a més de guardar els valors, guarden també una **puntuació** (**score**) per a cada valor, i **Redis** mantindrà el conjunt **ordenat** per aquesta puntuació.

Els valors no es podran repetir, però sí les puntuacions.

Alguns dels comandos seran iguals que els del **Set**, ja que un conjunt ordenat no deixa de ser un conjunt, però amb la informació de la puntuació (i que no es poden repetir els valors). En aquesta ocasió començaran per **Z**.

I aquesta és la llista dels que veurem:

[zadd](#zadd)  ,  [zcard](#zcard)  ,  [zscore](#zscore)  ,  [zcount](#zcount)  ,  [zrange](#zrange)  ,  [zrangebyscore](#zrangebyscore)  ,  [zrank](#zrank)  ,  [zrem](#zrem)  ,  [zremrangebyscore](#zremrangebyscore)  ,  [zincrby](#zincrby)

<a name="zadd"></a>ZADD

Sintaxi

zadd clau puntuació1 valor1 puntuació2 valor2 puntuacióN valorN

Afegeix els valors al conjunt (creant la clau si és necessari) amb les puntuacions corresponents. Les puntuacions seran Strings de valors reals (float). No es poden repetir els valors, però sí les puntuacions. Si intentem introduir un valor repetit, el que farà serà actualitzar la puntuació. El comando tornarà el número d'elements que realment s'han afegit.

Exemples

127\.0.0.1:6379> zadd puntuacions 1 Nom1 2 Nom2 5 Nom3 4 Nom4
(integer) 4

127\.0.0.1:6379> zrange puntuacions 0 -1
\1) "Nom1"
\2) "Nom2"
\3) "Nom4"
\4) "Nom3"

<a name="zcard"></a>ZCARD

Sintaxi

zcard clau

Torna la cardinalitat, és a dir, el número d'elements del conjunt ordenat en l'actualitat.

Exemples

127\.0.0.1:6379> zcard puntuacions
(integer) 4

<a name="zscore"></a>ZSCORE

Sintaxi

zscore clau valor

Torna la puntuació (score) del valor especificat del conjunt ordenat. Si no existeix el valor o no existaix la clau, torna nil.

Exemples

127\.0.0.1:6379> zscore puntuacions Nom3
"5"

127\.0.0.1:6379> zscore puntuacions Nom7
(nil)

<a name="zcount"></a>ZCOUNT

Sintaxi

zcount clau min max

Torna el número de valors que estan entre les puntuacions especificades (ambdues incloses).

Exemples

127\.0.0.1:6379> zcount puntuacions 2 5
(integer) 3

<a name="zrange"></a>ZRANGE

Sintaxi

zrange clau inici final [withscores]

Torna els elements del conjunt ordenat que hi ha entre els index inici i final, ambdós inclosos. I es trauen per ordre ascentent de puntuació. El primer element és el 0. Es poden posar valors negatius, sent -1 l'últim, -2 el penúltim, ... Opcionalment podem posar **WITHSCORES** per a que ens torne també la puntuació de cada element

Exemples

127\.0.0.1:6379> zrange puntuacions 0 -1
\1) "Nom1"
\2) "Nom2"
\3) "Nom4"
\4) "Nom3"

127\.0.0.1:6379> zrange puntuacions 0 -1 withscores
\1) "Nom1"
\2) "1"
\3) "Nom2"
\4) "2"
\5) "Nom4"
\6) "4"
\7) "Nom3"
\8) "5"

Si vulguérem traure el conjunt en ordre invers de puntuació, utilitzaríem el comando **ZREVRANGE** (**reverse range**).

127\.0.0.1:6379> zrevrange puntuacions 0 -1 withscores
\1) "Nom3"
\2) "5"
\3) "Nom4"
\4) "4"
\5) "Nom2"
\6) "2"
\7) "Nom1"
\8) "1"

<a name="zrangebyscore"></a>ZRANGEBYSCORE

Sintaxi

zrangebyscore clau min max [withscores]

Torna els elements del conjunt ordenat que tenen una puntuació compresa entre **min** i **max** (ambdues incloses). I es trauen per ordre ascentent de puntuació. Opcionalment podem posar **WITHSCORES** per a que ens torne també la puntuació de cada element. 

Exemples

127\.0.0.1:6379> zrangebyscore puntuacions 2 5
\1) "Nom2"
\2) "Nom4"
\3) "Nom3"

127\.0.0.1:6379> zrangebyscore puntuacions 2 5 withscores
\1) "Nom2"
\2) "2"
\3) "Nom4"
\4) "4"
\5) "Nom3"
\6) "5"

Si vulguérem que les puntuacions foren estrictament majors que la puntiuació mínima i/o estrictament menor que la puntuació màxima, posaríem un **parèntesi** davant de **min** i/o **max**:

127\.0.0.1:6379> zrangebyscore puntuacions 2 (5 withscores
\1) "Nom2"
\2) "2"
\3) "Nom4"
\4) "4"

I si vulguérem traure el conjunt en ordre invers de puntuació, utilitzaríem el comando **ZREVRANGEBYSCORE** (**reverse range**). Cuideu que com va en ordre invers, ara el valor màxim ha de ser el primer, i el mínim el segon.

127\.0.0.1:6379> zrevrangebyscore puntuacions 5 2 withscores
\1) "Nom3"
\2) "5"
\3) "Nom4"
\4) "4"
\5) "Nom2"
\6) "2"

<a name="zrank"></a>ZRANK

Sintaxi

zrank clau valor

Torna el número d'ordre de l'element amb el valor especificat. El primer valor és el 0. Si no existeix, torna **nil**.

Exemples

127\.0.0.1:6379> zrank puntuacions Nom1
(integer) 0

127\.0.0.1:6379> zrank puntuacions Nom4
(integer) 2

127\.0.0.1:6379> zrank puntuacions Nom7
(nil)

Si volem saber el número d'ordre però des del final de la llista (en ordre invers), hem d'utilitzar **ZREVRANK**:

127\.0.0.1:6379> zrevrank puntuacions Nom1
(integer) 3

127\.0.0.1:6379> zrevrank puntuacions Nom4
(integer) 1

<a name="zrem"></a>ZREM

Sintaxi

zrem clau valor1 valor2 valorN

Elimina els elements amb els valors especificats. Si algun valor no existeix, senzillament l'ignora. Torna el número d'elements realment eliminats.

Exemples

127\.0.0.1:6379> zrem puntuacions Nom1
(integer) 1

127\.0.0.1:6379> zrange puntuacions 0 -1 withscores
\1) "Nom2"
\2) "2"
\3) "Nom4"
\4) "4"
\5) "Nom3"
\6) "5"

<a name="zremrangebyscore"></a>ZREMRANGEBYSCORE

Sintaxi

zremrangebyscore clau min max

Elimina els elements amb puntuació compresa entre el mínim i el màxim de forma inclusiva. Si volem fer-ho de forma excusiva (sense incloure les puntuacions dels extrems) posarem un parèntesi davant del mínim i/o el màxim. Torna el número d'elements realment eliminats.

Exemples

127\.0.0.1:6379> zremrangebyscore puntuacions (2 4
(integer) 1

127\.0.0.1:6379> zrange puntuacions 0 -1 withscores
\1) "Nom2"
\2) "2"
\3) "Nom3"
\4) "5"

<a name="zincrby"></a>ZINCRBY

Sintaxi

zincrby clau increment valor

Incrementa la puntuació de l'element especificat. El valor de la puntuació a incrementar és un número real. Torna el valor la puntuació final de l'element. Si l'element no existia, l'inserirà, assumint una puntuació inicial de 0.

Exemples

127\.0.0.1:6379> zincrby puntuacions 1.5 Nom2
"3.5"

127\.0.0.1:6379> zincrby puntuacions 2.75 Nom5
"2.75"

127\.0.0.1:6379> zrange puntuacions 0 -1 withscores
\1) "Nom5"
\2) "2\.75"
\3) "Nom2"
\4) "3\.5"
\5) "Nom3"
\6) "5"

[« Anterior](235__set.md) | [Següent »](3__mongodb.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
