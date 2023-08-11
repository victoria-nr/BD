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

[« Anterior](index.md) | [Següent »](2__bd_clauvalor_redis.md)
# <a name="main"></a>**1 - Introducció**
En els últims anys estan eixint noves Bases de Dades que estan fugint del que ells anomenen "rigidesa" de les Bases de Dades Relacionals, on les dades estan molt estructurades: taules amb camps perfectament definits, i amb les restriccions que hem vist que es poden crear.

I si vulguérem guardar dades poc estructurades? Per exemple dels usuaris d'una determinada organització, que no sempre ens guardem la mateixa informació: unes vegades ens guardem el telèfon, altres no, altres ens guardem més d'un telèfon; altres vegades ens volem guardar la seua pàgina web, altres vegades les aficions, ... En el model relacional, molt estructurat, hauríem de preveure tots els camps necessaris, i en cas de que sorgira la necessitat d'una nova informació hauríem de canviar l'estructura de la taula.

O un altre exemple, volem guardar senzillament unes quantes "variables" de forma permanent. Podria ser per exemple guardar les preferències de l'usuari en una aplicació per a dispositius mòbils. Si ho dissenyàrem en una taula, seria una taula amb molts camps, però que després només hi haurà una fila, la de l'usuari.

Un altre exemple seria guardar informació de documents XML o JSON, els estàndars d'intercanvi d'informació. En el Model Relacional hauríem de guardar el document XML o JSON pràcticament en un camp, tot junt, i seria costós buscar dins de l'estructura XML o JSON.

Per a salvar aquestos inconvenients mencionats han eixit una sèrie d'iniciatives noves que s'han agrupat en el terme **NoSQL** (Not Only SQL). Són en definitiva Bases de Dades que no estan basades en el Model Relacional, i que en determinades ocasions poden ser més eficients que les Bases de Dades Relacionals precisament per fugir de la rigidesa que proporciona aquest model, amb dades tan ben estructurades. El terme clau és "en determinades ocasions", és a dir, per a guardar un determinat tipus d'informació. Així ens trobarem distints tipus de Bases de Dades NoSQL, depenent del tipus d'informació que vulguen guardar:

- **Bases de Dades Orientades a Objectes**, per a poder guardar objectes, com per exemple **DB4O**
- **Bases de Dades Orientades a Documents** (o simplement Bases de Dades Documentals), per a guardar documents de determinats tipus: XML, JSON, ... Per exemple **eXist** que guarda documents XML, o **MongoDB** que guarda la informació en un format similar a JSON.
- **Bases de Dades Clau-Valor**, per a guardar informació de forma molt senzilla, guardant únicament la clau (el nom de la propietat) i el seu valor
- **Bases de Dades Orientades a Grafs**, per a guardar estructures com els grafs, on hi ha una sèrie de nodes i arestes que comunicarien (relacionarien) els nodes
- Altres tipus com les **Bases de Dades Multivalor**, les **Bases de Dades Tabulars**, **Bases de Dades Orientades a Columna**, ...

En aquest tema només veurem una Base de Dades **Clau-Valor**, **Redis**, per la seua senzillesa; i dues Bases de Dades documentals, **MongoDB**, per la seua utilització actual, i eXist-db, que guarda documents XML.

[« Anterior](index.md) | [Següent »](2__bd_clauvalor_redis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
