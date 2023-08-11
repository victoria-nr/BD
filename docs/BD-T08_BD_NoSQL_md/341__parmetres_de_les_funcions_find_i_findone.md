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

[« Anterior](34__consulta_de_documents.md) | [Següent »](342__operadors_de_les_condicions.md)
# <a name="main"></a>**3.4.1 - Paràmetres de les funcions find() i findOne()**
Les funcions **find()** i **findOne()** són absolutament equivalents, amb l'úinca diferència que la primera torna tots els documents trobats, mentre que la segona només torna el primer document trobat.

Per una millor comprensió, utilitzarem únicament **find()**, per veure tots els resultats obtinguts.

La funció **find()** s'ha comparat tradicionalment amb la sentència SELECT de SQL. Sempre tornarà un conjunt de documents, que poden variar des de no tornar cap document, a tornar tots els de la col·lecció.

La funció **find()** pot tenir uns quants paràmetres.

- El primer indica una condició o criteri, i tornarà aquells documents de la col·lecció que acomplesquen la condició o criteri. Aquesta condició ve donada en forma de document (o objecte) JSON, i és com l'havíem vist en la funció **update()**:

db.col\_leccio1.find( { clau1 : valor1 } )

Tornarà tots els documents de la col·lecció **col\_leccio1** que tinguen el camp **clau1** i que en ella tinguen el valor **valor1**. Aquest criteri pot ser el complicat que faça falta, formant-lo en JSON. En definitiva, tornarà aquells documents que facen *matching* amb el document del criteri, és a dir, funcionaria com un **and**

db.col\_leccio1.find( { clau1 : valor1 , clau2 : valor2 } )

que tornaria aquells documents de la **col\_lecció1** que tenen el camp **clau1** amb el valor **valor1** i que tenen el camp **clau2** amb el valor **valor2**

Si no volem posar cap criteri, per a que els torne tots, no posem res com a paràmetre, o encara millor, li passem un document (objecte) buit, de manera que tots els documents de la col·lecció faran *matching* amb ell.

db.col\_leccio1.find( { } )

Tindrem açò present, sobretot quan ens toque utilitzar el segon paràmetre de **find**. Si no volem cap criteri, posarem el document buit com l'exemple anterior

- El segon paràmetre ens servirà per a delimitar els camps dels documents que es visualitzaran. També tindrà el format JSON d'un objecte al qual li posarem com a claus els diferents camps que volem que apareguen o no, i com a valor 1 per a que sí que apareguen i 0 per a que no apareguen.

Si posem algun camp a que sí que aparega (és a dir, amb el valor 1), els únics que apareixeran seran aquestos, a més del**\_id** que per defecte sempre apareix.

\> db.alumnes.find({},{nom:1})
{ "\_id" : ObjectId("56debe3017bf4ed437dc77c8"), "nom" : "Abel" }
{ "\_id" : ObjectId("56dfdbd136d8b095cb6bd57a"), "nom" : "Berta" }

Per tant si no volem que aparega **\_id** posarem:

\> db.alumnes.find({},{\_id:0})
{ "nom" : "Abel", "cognoms" : "Bernat Cantera", "edat" : 22, "adreça" : { "carrer" : "Major", "numero" : 7, "cp" : "12502" }, "nota" : [ 9.5, 9 ] }
{ "nom" : "Berta", "cognoms" : "Bernat Cantero" }

I si volem traure únicament el nom:

\> db.alumnes.find({},{nom:1,\_id:0})
{ "nom" : "Abel" }
{ "nom" : "Berta" }

Per últim, com que a partir d'ara utilitzarem documents més complicats, si volem que ens apareguen els camps que retornem d'una forma un poc més elegant o bonica (*pretty*), posarem aquesta funció al final: **find().pretty()**

\> db.alumnes.find().pretty()
{
`    `"\_id" : ObjectId("56debe3017bf4ed437dc77c8"),
`    `"nom" : "Abel",
`    `"cognoms" : "Bernat Cantera",
`    `"edat" : 22,
`    `"adreça" : {
`        `"carrer" : "Major",
`        `"numero" : 7,
`        `"cp" : "12502"
`    `},
`    `"nota" : [
`        `9.5,
`        `9
`    `]
}
{
`    `"\_id" : ObjectId("56dfdbd136d8b095cb6bd57a"),
`    `"nom" : "Berta",
`    `"cognoms" : "Bernat Cantero"
}

[« Anterior](34__consulta_de_documents.md) | [Següent »](342__operadors_de_les_condicions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
