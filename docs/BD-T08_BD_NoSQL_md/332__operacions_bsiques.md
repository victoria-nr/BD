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

[« Anterior](331__tipus_de_dades.md) | [Següent »](323__operacions_dactualitzaci_avanada.md)
# <a name="main"></a>**3.3.2 - Operacions bàsiques**
En aquest punt anem a veure les operacions més bàsiques, per a poder treballar sobre exemples pràctics, i així disposar ja d'unes dades inicials per a practicar.

Inserció elemental

La funció **insert** afegirà documents a una col·lecció. En el paràmetre posem el document directament, o una variable que continga el document. Si la col·lecció no existia, la crearà i després afegirà el document. En la següent sentència estem treballant sobre la col·lecció **exemple**, que segurament ja existirà de quan vam la pregunta 3.1 d'instal·lació de MongoDB, que per a provar vam inserir un document. Però si no existia, la crearà sense problemes.

\> db.exemple.insert({ msg2 : "Com va la cosa?"})
WriteResult({ "nInserted" : 1 })

Acabem d'inserir un nou document, i així ens ho avisa ( **{ "nInserted" : 1 }** , s'ha inserit un document). Automàticament haurà creat un element **\_id** de tipus **ObjectId**, ja que li fa falta per a identificar el document entre tots els altres de la col·lecció.

I en aquest exemple ens guardem el document en la variable **doc**, i després l'inserim

\> doc = { msg3 : "Per ací no ens podem queixar ..."}
{ "msg3" : "Per ací no ens podem queixar ..." }
\> db.exemple.insert(doc)
WriteResult({ "nInserted" : 1 })

També ens indica que ha inserit un document. I haurà creat també el camp **\_id** com veurem en el següent punt

Lectura

Tenim dues funcions per a recuperar informació: ***find*** i ***findOne***.

- **find()** : recuperarà tots els documents de la col·lecció, encara que podrem posar criteris per a que ens torne tots els documents que acomplesquen aquestos criteris (ho veurem més avant).
- **findOne()** : només tornarà un document, en principi el primer. Pot ser sobre tots els documents (i per tant seria el primer document), o posar una condició, i tornaria el primer que acomplirà la condició.

Exemple de **find()**:

\> db.exemple.find()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?" }
{ "\_id" : ObjectId("56ce31f6c61e04ba81def50c"), "msg2" : "Com va la cosa?" }
{ "\_id" : ObjectId("56ce3237c61e04ba81def50d"), "msg3" : "Per ací no ens podem queixar ..." }
\>

Exemple de **findOne()**:

\> db.exemple.findOne()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?" }
\>

En tots els casos podem comprovar que és cert el que veníem afirmant, que ha creat automàticament l'element **\_id** per a cada document guardat. Evidentment, cadascú de nosaltres tindrà una valors diferents.

Inserció especificant el id

Ara que ja sabem consultar els document de la col·lecció amb **find()** anem a continuar les insercions de documents, per veure les possibilitats que tenim.

En els document que hem inserit fins el moment, no hem especificat el camp **\_id**, i Mongo l'ha generat automàticament de tipus **ObjectId**.

Però nosaltres podrem posar aquest camp **\_id** amb el valor que vulguem. Això sí, haurem d'estar segurs que aquest valor no l'agafa cap altre dcument de la col·lecció, o ens donarà un error.

Així per exemple anem a inserir la informació d'uns alumnes. Els posarem en una col·lecció nova anomenada **alumnes**, i els intentarem posar un **\_id** personal. Per exemple posarem els números 51, 52, 53, ...

\> db.alumnes.insert ({\_id: 51 , nom: "Rebeca" , cognoms: "Martí Peral"})
WriteResult({ "nInserted" : 1 })

Ha anat bé, i si mirem els documents que tenim en la col·lecció, comprovarem que ens ha respectat el **\_id**:

\> db.alumnes.find()
{ "\_id" : 51, "nom" : "Rebeca", "cognoms" : "Martí Peral" }
\>

Però si intentem inserir un altre document amb el mateix **\_id** (51), ens donarà error:

\> db.alumnes.insert ({\_id: 51 , nom: "Raquel" , cognoms: "Gomis Arnau"})
WriteResult({
`    `"nInserted" : 0,
`    `"writeError" : {
`        `"code" : 11000,
`        `"errmsg" : "E11000 duplicate key error collection: test.alumnes index: \_id\_ dup key: { : 51.0 }"
`    `}
})
\>

Ens avisa que estem duplicant la *clau* *principal* , és a dir l'identificador.

Inserció múltiple: insertMany()

Quan els documents que volem inserir són senzills, podem inserir més d'un a la vegada, posant dis del **insert()** un **array** amb tots els elements. Depenent de la versió de Mongo, aquesta operació l'haurem de fer per mig d'una altre sentència: **insertMany()** En el següent exemple creem uns quants nombres primers en la col·lecció del mateix nom:

\> db.nombresprimers.insertMany( [ {\_id:2} , {\_id:3} , {\_id:5} , {\_id:7} , {\_id:11} , {\_id:13} , {\_id:17} , {\_id:19} ] )
BulkWriteResult({
`    `"writeErrors" : [ ],
`    `"writeConcernErrors" : [ ],
`    `"nInserted" : 8,
`    `"nUpserted" : 0,
`    `"nMatched" : 0,
`    `"nModified" : 0,
`    `"nRemoved" : 0,
`    `"upserted" : [ ]
})
\>

Ens avisa que ha fet 8 insercions, i ací els tenim:

\> db.nombresprimers.find()
{ "\_id" : 2 }
{ "\_id" : 3 }
{ "\_id" : 5 }
{ "\_id" : 7 }
{ "\_id" : 11 }
{ "\_id" : 13 }
{ "\_id" : 17 }
{ "\_id" : 19 }
\>

Esborrat

Per a esborrar un document d 'una col·lecció utilitzarem la funció **remove**, passant-li com a paràmetre la condició del document o documents a esborrar.

\> db.nombresprimers.remove( {"\_id" : 19} )
WriteResult({ "nRemoved" : 1 })
\>

Ens avisa que ha esborrat un document.

La condició no cal que siga sobre el camp **\_id**. Pot ser sobre qualsevol camp, i esborrarà tots els que coincideixen.

\> db.exemple.remove( {"msg3" : "Per ací no ens podem queixar ..."} )
WriteResult({ "nRemoved" : 1 })
\>

També tenim la possibilitat d'esborrar tota una col·lecció amb la funció **drop()**. Pareu atenció perquè és molt senzilla d'eliminar, i per tant, potencialment molt perillosa.

\> db.nombresprimers.drop()
true
\>

Actualització: update() i updateMany()

La funció ***update*** servirà per a actualitzar un document ja guardat. Pot tindre tres paràmetres, els dos primers obligatoris:

- El primer paràmetre serà la condició per a trobar el document (o els documents) que es va a actualitzar.
- El segon paràmetre serà el nou document que substituirà l'anterior
- El tercer paràmetre és per a especificar opcions addicionals, com per exemple si es modifica només un document o tots els que acompleixen la condició

Per exemple, si mirem les dades actuals:

\> db.exemple.find()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?" }
{ "\_id" : ObjectId("56ce31f6c61e04ba81def50c"), "msg2" : "Com va la cosa?" }

Podem comprovar el contingut del segon document, el que te **msg2**. Anem a modificar-lo: en el primer paràmetre posem condició de búsqueda (només hi haurà un) i en el segon posem el nou document que substituirà l'anterior

\> db.exemple.update( {msg2:"Com va la cosa?"} , {msg2:"Què? Com va la cosa?"} )
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

Observeu que la contestació del **update()** és que ha fet **match** (hi ha hagut coincidència) amb un document, i que ha modificat un. Si no en troba cap, no donarà error, senzillament dirà que ha fet match amb 0 documents, i que ha modificat 0 documents. Mirem com efectivament ha canviat el segon document

\> db.exemple.find()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?" }
{ "\_id" : ObjectId("56ce31f6c61e04ba81def50c"), "msg2" : "Què? Com va la cosa?" }

Ens vindran molt bé les variables per a les actualitzacions, ja que en moltes ocasions serà modificar lleugerament el document, canviant o afegint algun element. Ho podrem fer còmodament amb la variable: primer guardem el document a modificar en una variable; després modifiquem la variable; i per últim fem l'operació d'actualització. Evidentment si tenim alguna variable amb el contingut del document ens podríem estalviar el primer pas.

\> doc1 = db.exemple.findOne()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?" }

\> doc1.titol = "Missatge 1"
Missatge 1

\> db.exemple.update( {msg:"Hola, què tal?"} , doc1)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
\> db.exemple.findOne()
{
`    `"\_id" : ObjectId("56ce310bc61e04ba81def50b"),
`    `"msg" : "Hola, què tal?",
`    `"titol" : "Missatge 1"
}
\>

**Opcions**

Com havíem comentat al principi de la pregunta, es pot posar un tercer paràmetre per a especificar una sèrie d'opcions. Només en veurem una: la possibilitat de dir que es modifiquen tots els documents que acomplesquen la condició del primer paràmetre. Per defecte, si no posem aquesta opció, es modificarà únicament el primer document que acompleix la condició. Si volem que es modifiquen tots els documents que acompleixen la condició haurem de posar com a tercer paràmetre:

{ multi: true }

Per exemple, suposem que tenim dos documents amb el camp **msg** amb el valor "Hola, què tal?, aleshores, amb aquesta sentència es modificarien els dos:

\> db.exemple.update( {msg:"Hola, què tal?"} , doc1, {multi:true})
WriteResult({ "nMatched" : 2, "nUpserted" : 0, "nModified" : 2 })

` `Està marcat en roig, perquè segurament no tindrem 2 documents amb aquesta condició.

També ho aconseguiríem amb la funció **updateMany()**, que modificarà tots els documents que acomplesquen la condició. Mo caldrà, evidentment, posar-li el tercer paràmetre:

\> db.exemple.updateMany( {msg:"Hola, què tal?"} , doc1)
WriteResult({ "nMatched" : 2, "nUpserted" : 0, "nModified" : 2 })

També està marcat en roig perquè segurament no tindrem 2 documents amb aquesta condició.

Funció Save

Hem vist la manera d'inserir nous documents amb **insert()** i d'actualitzar documents existents amb **update()**. Però si intentem inserir un document ja existent (la manera de saber-ho és pel camp **\_id**) ens donarà error. I si intentem actualitzar un document no existent, no donarà error, però no actualitzarà res.

La funció **save()** és una barreja dels dos: si el document que anem a salvar ja existeix, doncs el modificarà, i si no existeix el crearà.

Provem-ho amb un exemple, i aprofitem-nos que en la variable **doc1** tenim el contingut d'un document. Fem una modificació, per exemple afegint el camp destinatari:

\> doc1.destinatari = "Ferran"
Ferran

\> doc1
{
`    `"\_id" : ObjectId("56ce310bc61e04ba81def50b"),
`    `"msg" : "Hola, què tal?",
`    `"titol" : "Missatge 1",
`    `"destinatari" : "Ferran"
}

Anem a guardar-lo amb **save()**:

\> db.exemple.save(doc1)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

Ja ens avisa qiue com ha trobat el document (**"nMatched : 1"**) ha modificat un. Efectivament, mirem com ha modificat el document existent:

\> db.exemple.find()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?", "titol" : "Missatge 1", "destinatari" : "Ferran" }
{ "\_id" : ObjectId("56ce31f6c61e04ba81def50c"), "msg2" : "Què? Com va la cosa?" }

Anem a fer ara una modificació del camp **\_id**. A tots els efectes serà un document nou, ja que la manera d'identificar un document és per aquest camp:

\> doc1.\_id=100
100

\> doc1
{
`    `"\_id" : 100,
`    `"msg" : "Hola, què tal?",
`    `"titol" : "Missatge 1",
`    `"destinatari" : "Ferran"
}

I ara anem a fer el **save()** d'aquest document:

\> db.exemple.save(doc1)
WriteResult({ "nMatched" : 0, "nUpserted" : 1, "nModified" : 0, "\_id" : 100 })

Observeu com ara avisa que no n'ha trobat cap igual, i el que fa és inserir-lo (ens diu **nUpserted**, que és una barreja de **Up**dated i In**serted**; més avant tornarem a aquesta paraula)

\> db.exemple.find()
{ "\_id" : ObjectId("56ce310bc61e04ba81def50b"), "msg" : "Hola, què tal?", "titol" : "Missatge 1", "destinatari" : "Ferran" }
{ "\_id" : ObjectId("56ce31f6c61e04ba81def50c"), "msg2" : "Què? Com va la cosa?" }
{ "\_id" : 100, "msg" : "Hola, què tal?", "titol" : "Missatge 1", "destinatari" : "Ferran" }

Efectivament s'ha guardat com un nou document

[« Anterior](331__tipus_de_dades.md) | [Següent »](323__operacions_dactualitzaci_avanada.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
