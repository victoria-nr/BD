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

[« Anterior](321__connexi_al_servidor_de_linstitut.md) | [Següent »](331__tipus_de_dades.md)
# <a name="main"></a>**3.3 - Utilització de MongoDB**
Començarem la utilització de MongoDB des de la consola que havíem arrancat al final de la instal·lació.

Recordeu que tindrem dues teminals:

- Una amb el servidor en marxa (i que no hem de tancar): **mongod**
- Una altra amb el client que es connecta al servidor: **mongo**

En aquesta última consola del client podem utilitzar sentències del llenguatge **Javascipt**, però el que més ens interessarà, evidentment, són les sentències d'accés a dades. Del llenguatge Javascript pràcticament l'únic que utilitzarem són variables i algunes funcions.

Utilització de variables

Com camentàvem el que més utilitzarem del llenguatge **Javascript** és la utilització de variables, que ens pot ser molt útil en algunes ocasions. Podrem utilitzar-les durant la sessió, però evidentment no perduraran d'una sessió a l'altra.

Per a definir una variable podem posar opcionalment davant la paraula reservada **var**, però no és necessari. Posarem el nom de la variable, el signe igual, i a continuació el valor de la variable, que pot ser una constant, o una expressió utilitzant constants, operadors, altres variables, funcions de Javascript, ...

Especialment interessant són les variables que poden contenir un document JSON.

Per exemple:

\> a = 30
30
\> b=a/4
7\.5
\> Math.sqrt(b)
2\.7386127875258306
\> doc = {camp1: "Hola", camp2: 45, camp3: new Date()}
{
`    `"camp1" : "Hola",
`    `"camp2" : 45,
`    `"camp3" : ISODate("2016-02-23T19:10:29.560Z")
}
\>

Una variable de tipus JSON es podrà modificar molt facilment, tota ella, o algun dels elements. Per a arribar als elements posarem ***nom\_variable.nom\_camp***:

\> doc.camp4 = 3.141592
3\.141592

\> doc.camp5 = [ 2 , 4 , 6 , 8]
[ 2, 4, 6, 8 ]

I si ara intentem traure el contingut de la variable:

\> doc
{
`    `"camp1" : "Hola",
`    `"camp2" : 45,
`    `"camp3" : ISODate("2016-02-24T22:31:12.724Z"),
`    `"camp4" : 3.141592,
`    `"camp5" : [
`        `2,
`        `4,
`        `6,
`        `8
`    `]
}
\>

També hem de fer constar que en un document, que serà de tipus JSON (pràcticament), serà un conjunt de parelles clau-valor, amb algunes restriccions:

- El document (que moltes vegades l'associarem a objecte de JSON) va entre claus ( **{ }** )
- Els elements d'un objecte van separats per comes, i són parelles clau-valor.
- La clau no pot ser nula, ni repetir-se en el mateix objecte (sí en diferents objectes, clar)
- Els valors són dels tipus que veurem en la pregunta 3.2.1
- Un document guardat ha de contenir obligatòriament un camp anomenat **\_id**, i que contindrà un valor únic en la col·lecció i servirà per a identificar-lo. Si en guardar un document no li hem posat camp **\_id**, el generarà automàticament MongoDB.

[« Anterior](321__connexi_al_servidor_de_linstitut.md) | [Següent »](331__tipus_de_dades.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
