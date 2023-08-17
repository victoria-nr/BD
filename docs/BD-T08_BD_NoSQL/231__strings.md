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

[« Anterior](23__utilitzaci_de_redis.md) | [Següent »](232__keys.md)
# <a name="main"></a>**2.3.1 - Strings**
És el tipus de dades més senzill, més bàsic. Serà una cadena de caràcters de tipus ***binary* safe** en la qual normalment guardarem les habituals cadenes de caràcters, però que també podríem guardar imatges o objectes serialitzats de Java. La grandària màxima és de 512Mb.

Ara veurem els comandos més habituals que afecten a aquest tipus. Com a norma general, hem de ser conscients que els comandos no són sensibles a majúscules o minúscules, però les claus i els valors sí que ho són. És a dir, el comando **get** també es pot escriure **GET** o **Get**. Però la clau **Hola** és diferent de la clau **hola**.

Concretament, els comandos que veurem seran:

[get](#get)  ,  [set](#set)  , [setex](#setex)  ,  [psetex](#psetex)  ,  [mget](#mget)  ,  [mset](#mset)  ,  [append](#append)  ,  [strlen](#strlen)  ,  [getrange](#getrange)  ,  [setrange](#setrange)  ,  [incr](#incr)  ,  [decr](#decr)  ,  [incrby](#incrby)  ,  [decrby](#decrby)

<a name="get"></a>GET

Sintaxi

get clau

Torna el valor de la clau especificada, sempre que siga de tipus **String**. Si la clau és d'un altre tipus, donarà error. I si la clau no existeix, tornarà el valor especial ***nil*** .

Exemples

127\.0.0.1:6379> get clau\_1
"primera"
127\.0.0.1:6379> get clau\_2
(nil)

<a name="set"></a>SET

Sintaxi

set clau valor

Assigna a la clau especificada com a primer paràmetre el valor especificat com a segon paràmetre. Si el valor consta de més d'una paraula, haurà d'anar entre cometes dobles.

Redis sempre guardarà el valor com a string, encara que nosaltres pensem que li passem un valor enter o real.

I una altra característica és que si la clau existeix ja, matxacarà el seu contingut, com era de esperar.

Exemples

127\.0.0.1:6379> set clau\_2 segona
OK
127\.0.0.1:6379> set text "Un text amb més d'una paraula"
OK

127\.0.0.1:6379> set quatre 4
OK
127\.0.0.1:6379> get quatre
"4"
127\.0.0.1:6379> set pi 3.14159265359
OK
127\.0.0.1:6379> get pi
"3.14159265359"

***Nota***

Si poseu algun accent, en tornar el valor (fent get) us semblarà que no s'ha guardat bé. Sí que s'haurà guardat bé, el que passa és que posteriorment no es visualitza bé en fer el get. Es pot comprovar entrant en el client amb l'opció ***raw*** , és a dir **redis-cli --raw**

El comando **SET** té una opció molt interessant, que servirà per a donar un temps de vida a la clau, transcorregut el qual desapareix la clau (amb el seu valor, clar). Açò s'anomena ***temps d'expiració*** i s'aconsegueix amb el paràmetre **EX** del comando **SET** seguit del número de segons que volem que dure la clau.

Exemple

127\.0.0.1:6379> set clau\_3 tercera ex 10
OK
127\.0.0.1:6379> get clau\_3
"tercera"
127\.0.0.1:6379> get clau\_3
(nil)

Primer sí que existeix, però al cap de 10 segons ha deixat d'existir.

De forma equivalent es pot expressar el temps en milisegons, amb el paràmetre **PX** en compte de **EX**.

Havíem comentat al principi, que si en el moment de fer el **SET** la clau ja existia, es reemplaçarà el seu contingut. Podem modificar aquest comportament amb el paràmetre **NX** (Not eXists): si no existia la clau, la crearà amb el valor, però si ja existia, la deixarà com estava. Ens ho indicarà dient OK en cas de crear-la i NIL en cas de no crear-la perquà ja existia.

127\.0.0.1:6379> set clau\_4 quarta nx
OK
127\.0.0.1:6379> set clau\_1 quarta nx
(nil)
127\.0.0.1:6379> get clau\_4
"quarta"
127\.0.0.1:6379> get clau\_1
"primera"

I de forma inversa, si posem el paràmetre **XX**, si ja existeix la clau, reemplaçarà el valor, però si no existia, no farà res.

<a name="setex"></a>SETEX

Sintaxi

setex clau segons valor

Funciona igual que el **SET** amb el paràmetre **EX**: crearà la clau amb el valor, però tindrà una existència dels segons indicats.

<a name="psetex"></a>PSETEX

Sintaxi

psetex clau milisegons valor

Funciona igual que l'anterior, però el que especifiquem són els milisegons d'existència.

<a name="mget"></a>MGET

Sintaxi

mget clau1 clau2 clauN

Torna una llista de valors, els de les claus indicades.

Exemple

127\.0.0.1:6379> set mes1 gener
OK
127\.0.0.1:6379> set mes2 febrer
OK
127\.0.0.1:6379> set mes3 març
OK
127\.0.0.1:6379> mget mes1 mes2 mes3
\1) "gener"
\2) "febrer"
\3) "mar\xc3\xa7"

**Nota** 

Recordeu que els caràcters com vocals accentuades, ç, ñ, ... s'han introduït bé, però potser no es visualiten bé. Es pot evitar entrant en el client d'aquesta manera **redis-cli --raw**

Si alguna de les claus no exiteix, tornarà **nil** en el seu lloc

<a name="mset"></a>MSET

Sintaxi

mset clau1 valor1 clau2 valor2 clauN valorN

Assigna els valors corresponents a les claus. És una operació atòmica: es posen (o canvien) tots els valors a l'hora.

127\.0.0.1:6379> mset mes4 abril mes5 maig mes6 juny mes7 juliol
OK
127\.0.0.1:6379> mget mes1 mes2 mes3 mes4 mes5 mes6 mes7
\1) "gener"
\2) "febrer"
\3) "mar\xc3\xa7"
\4) "abril"
\5) "maig"
\6) "juny"
\7) "juliol"

Si no vulguérem reemplaçar valors, podríem utilitzar el comando **MSETNX**, totalment equivalent, però hauríem de tenir en compte que si alguna ja existeix i per tant no pot canviar el valor, no faria l'operació, és a dir, tampoc crearia les altres.

<a name="append"></a>APPEND

Sintaxi

append clau1 valor1

Si la clau no existeix la crea assignant-li el valor (com el **SET**), però si ja existeix, concatena el valor al final de la cadena que ja hi havia.

127\.0.0.1:6379> append salutacio Hola
(integer) 4
127\.0.0.1:6379> get salutacio
"Hola"
127\.0.0.1:6379> append salutacio ", com va?"
(integer) 13
127\.0.0.1:6379> get salutacio
"Hola, com va?"

<a name="strlen"></a>STRLEN

Sintaxi

strlen clau1

Torna el número de caràcters que hi ha en el valor de la clau. Si la clau no existeix, tornarà 0. Si la clau és d'un altre tipus, tornarà error.

127\.0.0.1:6379> strlen salutacio
(integer) 13
127\.0.0.1:6379> strlen sal
(integer) 0

<a name="getrange"></a>GETRANGE

Sintaxi

getrange clau1 inici final

Extrau una subcadena del valor de la clau (ha de ser de tipus **String**) des del número de caràcter d'inici fins al número del final (ambdós inclosos). El primer caràcter és el 0. Si posem de final un número major que l'últim, igual ho traurà fins el final.

Es poden posar també valor negatius que ens ajuden a agafar la cadena des del final. El -1 és l'últim caràcter, el -2 el penúltim, ... I es poden barrejar números positius i negatius. Així,  **rang 0 -1** és tota la cadena.

127\.0.0.1:6379> getrange salutacio 1 3
"ola"
127\.0.0.1:6379> getrange salutacio 6 50
"com va?"
127\.0.0.1:6379> getrange salutacio 6 -1
"com va?"
127\.0.0.1:6379> getrange salutacio -7 -5
"com"
127\.0.0.1:6379> getrange salutacio 0 -1
"Hola, com va?"

<a name="setrange"></a>SETRANGE

Sintaxi

setrange clau1 desplaçament valor

Substitueix part del valor de la cadena, a partir del desplaçament, amb el vaolr proporcionat. No s'admenten en desplaçament valors negatius.

127\.0.0.1:6379> get salutacio
"Hola, com va?"
127\.0.0.1:6379> setrange salutacio 4 ". C"
(integer) 13
127\.0.0.1:6379> get salutacio
"Hola. Com va?"

<a name="incr"></a>INCR

Sintaxi

incr clau1

A pesar de que Redis guarda els strings com a tals, com a cadenes de caràcters, en algunes ocasions és capaç de transformar la cadena a un número. És el cas del comando **INCR**, que converteix la cadena en un enter (si pot) i incrementa aquest valor en una unitat.

Si la clau no existeix la crea assumint que valia 0, i per tant després valdrà 1.

Si el valor de la clau no era un número enter, donarà un error.

127\.0.0.1:6379> set compt1 20
OK
127\.0.0.1:6379> get compt1
"20"
127\.0.0.1:6379> incr compt1
(integer) 21
127\.0.0.1:6379> get compt1
"21"
127\.0.0.1:6379> incr compt2
(integer) 1
127\.0.0.1:6379> get compt2
"1"
127\.0.0.1:6379> incr clau\_1
(error) ERR value is not an integer or out of range
127\.0.0.1:6379> set compt3 4.25
OK
127\.0.0.1:6379> incr compt3
(error) ERR value is not an integer or out of range

<a name="decr"></a>DECR

Sintaxi

decr clau1

Decrementa en una unitat el valor de la clau (senpre que siga un enter).

Pot agafar valors negatius.

Si la clau no existeix la crea assumint que valia 0, i per tant després valdrà -1.

127\.0.0.1:6379> decr compt2
(integer) 0
127\.0.0.1:6379> decr compt2
(integer) -1
127\.0.0.1:6379> get compt2
"-1"

<a name="incrby"></a>INCRBY

Sintaxi

incrby clau1 increment

Incrementa el valor de la clau en el número d'unitats indicat en **increment** (el valor ha de ser enter). L'increment pot ser negatiu.

127\.0.0.1:6379> incrby compt1 10
(integer) 31
127\.0.0.1:6379> incrby compt1 -20
(integer) 11

<a name="decrby"></a>DECRBY

Sintaxi

decrby clau1 decrement

Decrementa el valor de la clau el número d'unitat indicat en **decrement**.

127\.0.0.1:6379> decrby compt1 5
(integer) 6

[« Anterior](23__utilitzaci_de_redis.md) | [Següent »](232__keys.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
