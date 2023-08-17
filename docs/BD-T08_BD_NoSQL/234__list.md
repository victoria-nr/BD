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

[« Anterior](233__hash.md) | [Següent »](235__set.md)
# <a name="main"></a>**2.3.4 - List**
Les **Llistes** en **Redis** són llistes de Strings ordenades, on cada element està associat a un índex de la llista. Es poden recuperar els elements tant de forma ordenada (per l'índex) com accedint directament a una posició.

Els elements es poden afegir al principi, al final o també en una posició determinada.

La llista es crea en el moment en què s'insereix el primer element, i desapareix quan llevem l'últim element que quede.

Estan molt ben optimitzades per a la inserció i per a la consulta.

Els comandos que afecten a les llistes comencen quasi tots per **L**, excepte alguns que comencen per **R** indicant que fan l'operació per la dreta.

Per cert, els valors dels elements es poden repetir.

La llista de comandos que afecten a llistes que veurem és:

[lpush](#lpush)  ,  [rpush](#rpush)  ,  [lpop](#lpop)  ,  [rpop](#rpop)  ,  [lset](#lset)  ,  [lindex](#lindex)  ,  [linsert](#linsert)  ,  [lrange](#lrange)  ,  [llen](#llen)  ,  [lrem](#lrem)  ,  [ltrim](#ltrim)

<a name="lpush"></a>LPUSH

Sintaxi

lpush clau valor1 valor2 valorN

Introdueix els valors a la llista (creant la clau si és necessari). Les insereix en la primera posició, o també podríem dir que per l'esquerra (**Left PUSH**), imaginant que els elements estan ordenats d'esquerra a dreta. Si posem més d'un valor, s'aniran introduint sempre en la primera posició. El comando tornarà el número d'elements (strings) de la llista després de la inserció.

Exemples

127\.0.0.1:6379> lpush llista1 primera segona tercera
(integer) 3

127\.0.0.1:6379> lrange llista1 0 -1
\1) "tercera"
\2) "segona"
\3) "primera"

127\.0.0.1:6379> lpush llista1 quarta cinquena
(integer) 5

127\.0.0.1:6379> lrange llista1 0 -1
\1) "cinquena"
\2) "quarta"
\3) "tercera"
\4) "segona"
\5) "primera"

**Nota** 

Per a veure el contingut de la llista utilitzarem el comando **lrange llista 0 -1**, que torna la llista sencera. Veurem de forma més completa aquest comando amb posterioritat.

<a name="rpush"></a>RPUSH

Sintaxi

rpush clau valor1 valor2 valorN

Introdueix els valors a la llista (creant la clau si és necessari). Les insereix en l'última posició, o també podríem dir que per la dreta (**Right PUSH**), imaginant que els elements estan ordenats d'esquerra a dreta.  El comando tornarà el número d'elements (strings) de la llista després de la inserció.

Exemples

127\.0.0.1:6379> rpush llista1 sisena setena
(integer) 7

127\.0.0.1:6379> lrange llista1 0 -1
\1) "cinquena"
\2) "quarta"
\3) "tercera"
\4) "segona"
\5) "primera"
\6) "sisena"
\7) "setena"

<a name="lpop"></a>LPOP

Sintaxi

lpop clau

Torna i elimina el primer element (el de més a l'esquerra).

Exemples

127\.0.0.1:6379> lpop llista1
"cinquena"

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "segona"
\4) "primera"
\5) "sisena"
\6) "setena"

<a name="rpop"></a>RPOP

Sintaxi

rpop clau

Torna i elimina l'últim element (el de més a la dreta).

Exemples

127\.0.0.1:6379> rpop llista1
"setena"

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "segona"
\4) "primera"
\5) "sisena"

<a name="lset"></a>LSET

Sintaxi

lset clau index valor

Substitueix el valor de la posició indicada per l'índex. Tant la clau com l'element de la posició indicada han d'existir, sinó donarà error. Ara la **L** no significa **Left** sinó **List**.

La primera posició és la 0. I també es poden posar números negatius: -1 és l'últim, -2 el penúltim, ...

Exemples

127\.0.0.1:6379> lset llista1 2 quarta
OK

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "sisena"

127\.0.0.1:6379> lset llista1 -1 cinquena
OK

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "cinquena"

Observeu com es poden repetir els valors

<a name="lindex"></a>LINDEX

Sintaxi

lindex clau index

Torna l'element situat en la posició indicada per l'índex, **però sense eliminar-lo de la llista**.

Exemples

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "cinquena"

127\.0.0.1:6379> lindex llista1 0
"quarta"

127\.0.0.1:6379> lindex llista1 3
"primera"

127\.0.0.1:6379> lindex llista1 -1
"cinquena"

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "cinquena"

<a name="linsert"></a>LINSERT

Sintaxi

linsert clau BEFORE | AFTER valor1 valor2

Insereix el valor2 abans o després (segons el que triem) de la primera vegada que troba el valor1. No substitueix, sinó que insereix en una determinada posició. Els elements que van després de l'element introduït veuran actualitzat el seu índex.

Exemples

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "cinquena"

127\.0.0.1:6379> linsert llista1 AFTER quarta segona
(integer) 6

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "segona"
\3) "tercera"
\4) "quarta"
\5) "primera"
\6) "cinquena"

127\.0.0.1:6379> linsert llista1 BEFORE cinquena sisena
(integer) 7

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "segona"
\3) "tercera"
\4) "quarta"
\5) "primera"
\6) "sisena"
\7) "cinquena"

Si intentem inserir abans o després un element que no existeix, tornarà -1 indicant que no l'ha trobat i no farà la inserció.

127\.0.0.1:6379> linsert llista1 BEFORE desena setena
(integer) -1

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "segona"
\3) "tercera"
\4) "quarta"
\5) "primera"
\6) "sisena"
\7) "cinquena"

<a name="lrange"></a>LRANGE

Sintaxi

lrange clau inici final

Torna els elements de la llista que hi ha entre els index inici i final, ambdós inclosos. El primer element és el 0. Es poden posar valors negatius, sent -1 l'últim, -2 el penúltim, ...

Exemples

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "segona"
\3) "tercera"
\4) "quarta"
\5) "primera"
\6) "sisena"
\7) "cinquena"

127\.0.0.1:6379> lrange llista1 2 4
\1) "tercera"
\2) "quarta"
\3) "primera"

127\.0.0.1:6379> lrange llista1 1 -2
\1) "segona"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "sisena"

127\.0.0.1:6379> lrange llista1 4 4
\1) "primera"

<a name="llen"></a>LLEN

Sintaxi

llen clau

Torna el número d'elements de la llista

Exemples

127\.0.0.1:6379> llen llista1
(integer) 7

<a name="lrem"></a>LREM

Sintaxi

lrem clau número valor

Elimina elements de la llista que coincidisquen amb el valor proporcionat. Ja sabem que els valors es poden repetir. Amb el número indiquem quants elements volem que s'esborren: si posem 1 s'esborrarà el primer element amb aquest valor, si posem 2 s'esborraran els dos primers elements (els de més a l'esquerra) que tingen aquest valor. Si posem 0 s'esborraran tots els elements amb aquest valor

Exemples

127\.0.0.1:6379> rpush llista1 segona
(integer) 8

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "segona"
\3) "tercera"
\4) "quarta"
\5) "primera"
\6) "sisena"
\7) "cinquena"
\8) "segona"

127\.0.0.1:6379> lrem llista1 1 segona
(integer) 1

127\.0.0.1:6379> lrange llista1 0 -1
\1) "quarta"
\2) "tercera"
\3) "quarta"
\4) "primera"
\5) "sisena"
\6) "cinquena"
\7) "segona"

127\.0.0.1:6379> lrem llista1 0 quarta
(integer) 2

127\.0.0.1:6379> lrange llista1 0 -1
\1) "tercera"
\2) "primera"
\3) "sisena"
\4) "cinquena"
\5) "segona"

<a name="ltrim"></a>LTRIM

Sintaxi

ltrim clau inici final

Elimina els elements que queden fora dels índex inici i final, és a dir elimina els que estiguen a l'esquerra d'inici, i els que estiguen a la dreta de final.

Exemples

127\.0.0.1:6379> ltrim llista1 1 -2
OK

127\.0.0.1:6379> lrange llista1 0 -1
\1) "primera"
\2) "sisena"
\3) "cinquena"

[« Anterior](233__hash.md) | [Següent »](235__set.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
