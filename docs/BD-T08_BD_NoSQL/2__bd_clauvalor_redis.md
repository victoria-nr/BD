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

[« Anterior](1__introducci.md) | [Següent »](21__installaci_de_redis.md)
# <a name="main"></a>**2 - BD Clau-Valor: Redis**
Segurament de tots els tipus de Bases de Dades NoSQL existents, la de més fàcil comprensió és la **Base de Dades Clau-Valor**. En ella s'aniran guardant parelles clau-valor, és a dir, el nom d'una determinada propietat i el seu valor. La clau ha de ser única, és a dir, no es pot repetir ja que en cas contrari no es podria tornar a recuperar.

Per tant no hi ha definició de taules ni cap altra estructura; es van guardant parelles clau-valor i prou. En el moment de recuperar la informació veurem que podrem obtenir el contingut d'una clau, o el de més d'una al mateix temps.

L'exemple que veurem de Base de Dades Clau-Valor és **Redis**, molt famosa per a seua potència i eficiència.

La clau sempre és de tipus String, i com ja hem comentat no poden haver dues claus iguals. En canvi en Redis els valors poden ser de 5 tipus diferents:

- **Cadenes de caràcters (String)**. Per exemple: **nom\_1 --> Albert**
- **Registres (Hashes)** que seran claus que tindran subcamps (sub-claus). Per exemple: **empleat\_1 --> [ nom="Albert" , departament="10" , sou="1000.0" ]**
- **Llistes (Lists)** que són conjunts ordenats de valors. Per exemple: **llista\_1 --> { "Primer" , "Segon" , "Tercer" }**
- **Conjunts (Sets)** són conjunts desordenats de valors. No importa el seu ordre, i de fet serà impredictible l'ordre amb el qual els torna Redis. Per exemple: **colors --> { "Blau" , "Verd" , "Roig" }**
- **Conjunts Ordenats (Sorted Sets)**. Ja veurem la diferència entre llistes i conjunts ordenats.

Algunes característiques de Redis són:

- És una arquitectura client-servidor
- És extraordinàriament eficient quan es pot carregar tota en memòria, encara que si no pot carregar-la també funcionarà de forma molt ràpida. I a més manté una sincronització constant a disc per a fer les dades persistents. Aquesta tasca la fa en segon pla, de manera que no afecta al servei.
- Per a poder suportar ratios de lectura molt alts fa una replicació master/slave, és a dir que pot haver més d'un servidor, i un és el que actua de master i els altres són rèpliques del primer. El slave rep una còpia inicial de la Base de Dades sencera. A mida que es van realitzant escriptures en el master, es van enviant a tots els slaves connectats. Els clients es poden connectar als distints servidors, bé siga al master o als slaves, sense haver de carregar sempre al master.

[« Anterior](1__introducci.md) | [Següent »](21__installaci_de_redis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
