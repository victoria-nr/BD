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

[« Anterior](231__strings.md) | [Següent »](233__hash.md)
# <a name="main"></a>**2.3.2 - Keys**
Ara anem a veure comandos que ens permeten treballar amb les claus, per a buscar-les, veure si existeixen, etc. No importarà el tipus de les claus (de moment només hem treballat amb claus de tipus **String**, però si ja en tinguérem dels altres tipus també es veurien afectades). En cap cas d'aquestos comandos accedirem al valor de les claus.

La llista de comandos de claus que veurem és:

[keys](#keys)  ,  [exists](#exists)  ,  [del](#del)  ,  [type](#type)  ,  [rename](#rename)  ,  [renamenx](#renamenx)  ,  [expire](#expire)  ,  [pexpire](#pexpire)  ,  [ttl](#ttl)  ,  [pttl](#pttl)  ,  [persist](#persist)

<a name="keys"></a>KEYS

Sintaxi

keys patró

Torna totes les claus que coincideixen amb el patró. En el patró podem posar caràcters comodí:

- **\*** : equival a 0 o més caràcters. Per exemple "Mar\*a" podria tornar "Mara", "Maria", "Marta", "Margarita", ...
- **?** : equival exactament a un caràcter. Per exemple "Mar?a" podria tornar "Maria" o "Marta",  però no "Mara", "Margarita", ...
- **[ab]** : serà cert si en el lloc corresponent hi ha un dels caràcters especificats entre els claudàtors. Per exemple "Mar[it]a" podria tornar "Maria" o "Marta", però no "Marga"

Per a tornar totes les claus utilitzarem **keys \***

127\.0.0.1:6379> keys \*
` `1) "mes3"
` `2) "salutacio"
` `3) "pi"
` `4) "clau\_4"
` `5) "compt2"
` `6) "mes6"
` `7) "mes1"
` `8) "mes4"
` `9) "clau\_1"
\10) "compt3"
\11) "quatre"
\12) "mes7"
\13) "mes2"
\14) "mes5"
\15) "compt1"
\16) "clau\_2"
\17) "text"

127\.0.0.1:6379> keys mes?
\1) "mes5"
\2) "mes3"
\3) "mes7"
\4) "mes2"
\5) "mes6"
\6) "mes4"
\7) "mes1"

127\.0.0.1:6379> keys c\*
\1) "clau\_4"
\2) "compt2"
\3) "clau\_1"
\4) "compt3"
\5) "compt1"
\6) "clau\_2"

127\.0.0.1:6379> keys mes[125]
\1) "mes5"
\2) "mes2"
\3) "mes1"

**Nota**

L'ordre en el qual es mostraran les claus no té per què ser igual per a tots nosaltres. Él més normal és que cadascú de nosaltres tinga un ordre diferent. Açò té a veure amb els conjunts (**set**), un tipus de dades que veurem més avant.

<a name="exists"></a>EXISTS

Sintaxi

exists clau

Torna 1 si la clau existeix, i 0 si no existeix. No importa de quin tipus siga la clau.

127\.0.0.1:6379> exists clau\_1
(integer) 1
127\.0.0.1:6379> exists clau\_25
(integer) 0

<a name="del"></a>DEL

Sintaxi

del clau1 clau2 clauN

Elimina la clau o claus especificades. Si posem més d'una clau i alguna no existeix, la ignorarà i sí que esborrarà les altres.

127\.0.0.1:6379> del compt2
(integer) 1
127\.0.0.1:6379> del mes6 mes7 mes8 mes9
(integer) 2

Observeu que ens indica quantes claus ha esborrat. En el primer exemple ha esborrat la clau especificada, i en el segon diu que ha esborrat 2, que seran **mes6** i **mes7**, ja que **mes8** i **mes9** no existien.

<a name="type"></a>TYPE

Sintaxi

type clau

Torna el tipus de la clau especificada. Els valors possibles són:

- string
- hash
- list
- set
- zset (conjunt ordenat)

Exemples

127\.0.0.1:6379> type clau\_1
string

<a name="rename"></a>RENAME

Sintaxi

rename clau novaclau

Canvia el nom de la clau a la clau nova, conservant el valor. Dóna error si la clau antiga no existeix. Si la clau nova ja existia reemplaçarà el seu valor.

Exemples

127\.0.0.1:6379> get salutacio
"Hola. Com va?"
127\.0.0.1:6379> rename salutacio saludar
OK
127\.0.0.1:6379> get salutacio
(nil)
127\.0.0.1:6379> get saludar
"Hola. Com va?"
127\.0.0.1:6379> rename clau\_22 clau\_23
(error) ERR no such key

<a name="renamenx"></a>RENAMENX

Sintaxi

renamenx clau novaclau

Igual que l'anterior però únicament si la clau nova no existia. Si ja existia no fa res (tornant 0 per a indicar-h0).

Exemples

127\.0.0.1:6379> renamenx compt1 compt3
(integer) 0
127\.0.0.1:6379> get compt1
"9"

Estem suposant que la clau **compt3** ja existeix

<a name="expire"></a>EXPIRE

Sintaxi

expire clau segons

Assigna com a temps d'expiració de la clau els segons especificats. Si ja tenia temps d'expiració, el modifica posant-li aquest valor especificat.

En cas que a una clau amb temps d'expiració li canviem el nom amb **RENAME**, continuarà amb temps d'expiració que li quedava.

<a name="pexpire"></a>PEXPIRE

Sintaxi

pexpire clau milisegons

El mateix però en milisegons

<a name="ttl"></a>TTL

Sintaxi

ttl clau

Torna el temps de vida (fins l'expiració) d'una clau. Si la clau no té temps d'expiració, torna -1.

Exemples

127\.0.0.1:6379> expire compt3 10
(integer) 1
127\.0.0.1:6379> ttl compt3
(integer) 6
127\.0.0.1:6379> ttl compt3
(integer) 3
127\.0.0.1:6379> ttl compt3
(integer) 0
127\.0.0.1:6379> get compt3
(nil)

<a name="pttl"></a>PTTL

Sintaxi

pttl clau

Igual que l'anterior, però ens torna el temps en milisegons.

<a name="persist"></a>PERSIST

Sintaxi

persist clau

Elimina el temps d'expiració d'una clau, si és que en tenia. Ara la clau no expirarà mai.

Exemples

127\.0.0.1:6379> expire compt1 20
(integer) 1
127\.0.0.1:6379> ttl compt1
(integer) 12
127\.0.0.1:6379> ttl compt1
(integer) 7
127\.0.0.1:6379> persist compt1
(integer) 1
127\.0.0.1:6379> ttl compt1
(integer) -1
127\.0.0.1:6379> get compt1
"9"

[« Anterior](231__strings.md) | [Següent »](233__hash.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
