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

[« Anterior](232__keys.md) | [Següent »](234__list.md)
# <a name="main"></a>**2.3.3 - Hash**
Ja havíem comentat que el tipus **Hash** és una espècie de registre, amb subcamps (en realitat hauríem de dir sub-claus). Pot tenir qualsevol número de subcamps que seran de tipus String.

**Redis** és molt eficient en quant a l'espai que ocupen els **Hash**, i sobretot en el temps de recuperació de les dades.

Els comandos que vam veure per al **String** no es poden aplicar al **Hash**. Tanmateix els comandos del **Hash** són molt similars a aquells, començant sempre per **H**.

Veurem els següents comandos:

[hset](#hset)  ,  [hget](#hget)  ,  [hgetall](#hgetall)  ,  [hdel](#hdel)  ,  [hkeys](#hkeys)  ,  [hvals](#hvals) ,  [hmget](#hmget)   ,  [hmset](#hmset)  ,  [hexists](#hexists)  ,  [hsetnx](#hsetnx)  ,  [hincrby](#hincrby)

<a name="hset"></a>HSET

Sintaxi

hset clau camp valor

Assigna al camp especificat de la clau especificada el valor especificat. Si el valor consta de més d'una paraula, haurà d'anar entre cometes dobles.

Si la clau no existia, la crearà, i si ja existia, senzillament afegirà el camp. I si d'aquesta clau  ja existia el camp, modificarà el seu valor.

Evidentment, en claus diferents poden haver camps amb els mateixos noms.

Exemples

127\.0.0.1:6379> hset empleat\_1 nom Andreu
(integer) 1
127\.0.0.1:6379> hset empleat\_1 departament 10
(integer) 1
127\.0.0.1:6379> hset empleat\_1 sou 1000.0
(integer) 1

127\.0.0.1:6379> hset empleat\_2 nom Berta
(integer) 1
127\.0.0.1:6379> hset empleat\_2 sou 1500.0
(integer) 1

<a name="hget"></a>HGET

Sintaxi

hget clau camp

Torna el valor del camp de la clau. Si no existia (el camp o la clau) torna **nil**. Només podem especificar un camp.

Exemples

127\.0.0.1:6379> hget empleat\_1 nom
"Andreu"
127\.0.0.1:6379> hget empleat\_1 departament
"10"
127\.0.0.1:6379> hget empleat\_2 nom
"Berta"
127\.0.0.1:6379> hget empleat\_2 departament
(nil)

<a name="hgetall"></a>HGETALL

Sintaxi

hgetall clau

Torna una llista amb tots els camps i els seus valors de la clau. La seqüència és: camp1 valor1 camp2 valor2 ... Però no ens podem fiar que l'ordre siga el mateix ordre que quan el vam definir.

Exemples

127\.0.0.1:6379> hgetall empleat\_1
\1) "nom"
\2) "Andreu"
\3) "departament"
\4) "10"
\5) "sou"
\6) "1000\.0"

<a name="hdel"></a>HDEL

Sintaxi

hdel clau camp1 camp2 campN

Elimina el o els camps especificats. Si no existeixen algun d'ells, senzillament l'ignora i si que elimina els altres.

Exemples

127\.0.0.1:6379> hdel empleat\_1 departament
(integer) 1
127\.0.0.1:6379> hgetall empleat\_1
\1) "nom"
\2) "Andreu"
\3) "sou"
\4) "1000\.0"

<a name="hkeys"></a>HKEYS

Sintaxi

hkeys clau

Torna una llista amb els camps de la clau. Si la clau no existia, torna una llista buida

Exemples

127\.0.0.1:6379> hkeys empleat\_1
\1) "nom"
\2) "sou"

<a name="hvals"></a>HVALS

Sintaxi

hvals clau

Torna una llista amb els valors (únicament els valors) de tots els camps de la clau. Si la clau no existia, torna una llista buida

Exemples

127\.0.0.1:6379> hvals empleat\_1
\1) "Andreu"
\2) "1000\.0"

Altres Comandos

També existeixen altres comandos, de funcionament com cabria esperar (els hem vist tots en el cas de **String**):

- <a name="hmget"></a>**hmget**: Torna més d'un camp de la clau
- <a name="hmset"></a>**hmset**: assigna més d'un camp a una clau
- <a name="hexists"></a>**hexists**: indica si existeix el subcamp de la clau
- <a name="hsetnx"></a>**hsetnx**: assigna únicament en cas de que no existisca el camp.
- <a name="hincrby"></a>**hincrby**: incrementa el camp de la clau

[« Anterior](232__keys.md) | [Següent »](234__list.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
