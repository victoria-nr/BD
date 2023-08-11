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

[« Anterior](33__utilitzaci_de_mongodb.md) | [Següent »](332__operacions_bsiques.md)
# <a name="main"></a>**3.3.1 - Tipus de dades**
Els valors dels elements, és a dir de les parelles clau valor, poden ser d'una amplia gama de tipus. Fem un ràpid repàs.

En els exemples que van a continuació definim senzillament parelles clau-valor dels diferents tipus, o en tot cas ens ho guardem en variables, però no guardarem encara en la Base de Dades (ho farem en la següent pregunta).

Quan guardem en una variable es mostrarà el prompt, la definició de la variable i després el resultat d'haver guardat la variable. Utilitzarem requadres blancs. Els requadres grocs són únicament de la definició d'una clau-valor d'un determinat tipus

NULL

Més que un tipus de dades és un valor, millor dit, l'absència de valor

{ "x" : null }

BOOLEAN

El tipus booleà, que pot agafar els valors true o false.

{ "x" : true }

{ "y" : false }

NUMBER

Per defecte, el tiups de dades numèrics serà el de coma flotant (**float**), simple precisió. Si volem un altre tiups (enter, doble precisió, ...) ho haurem d'indicar expressament. Així els dos següents valors són float:

{ "x" : 3.14 }

{ "y" : 3 }

Si volem que siga estrictament enter, per exemple, haurem d'utilitzar una funció de conversió:

{ "x" : NumberDouble("3.14") }

{ "y" : NumberInt("3") }

STRING

Es pot guardar qualsevol cadena amb caràcters de la codificació UTF-8

{  x : "Hola, què tal?"}

DATE

Es guarda data i hora, i internament es guarden en milisegons des de l'any inicial. No es guara el *Time zone* , és a dir,* la desviació respecte a l'hora internacional.

{ x : ISODate("2016-02-24T11:15:27.471Z") }

Normalment utilitzarem funcions de tractament de la data-hora. L'anterior era per a convertir el string en data-hora. La següent és per a obtenir la data-hora actual:

{ x : new Date() }

És a dir, que si no posem paràmetre, ens dóna la data-hora actual. Però li podem posar com a paràmetre la data-hora que volem que genere. En aquest exemple, només posem data, per tant l'ho serà les 00:00:

\> z = new Date("2016-08-01")
ISODate("2016-08-01T00:00:00Z")

En aquest sí que posem una determinada hora, i observeu com hem deposar la T (Time) entre el dia i l'hora:

\> z = new Date("2016-08-01T10:00")
ISODate("2016-08-01T08:00:00Z")

És molt important que posem sempre **New Date()** per a generar una data-hora. Si posem únicament **Date()**, el que estem generant és un string (amb la data i hora, però un string):

\> z = Date("2016-08-01")
Fri Feb 26 2016 08:30:13 GMT+0100 (CET)

ARRAY

És un conjunt d'elements, cadascun de qualsevol tipus, encara que el més habitual és que siguen del mateix tipus. Van entre claudàtors ( **[ ]** ) i els elements separats per comes.

{ x : [ 2 , 4 , 6 , 8 ] }

Com comentàvem, cada element de l'array pot ser de qualsevol tipus:

{ y : [ 2 , 3.14 , "Hola" , new Date() ] }

En MongoDB podrem treballar molt bé amb arrays, i tindrem operacions per a poder buscar dins de l'array, modificar un element, crear índex, ...

DOCUMENTS (OBJECTES)

Els documents poden contenir com a elements uns altres documents (**objectes** en la terminologis¡a JSON, però **documents** en la terminologia de MongoDB).

Com sempre van entre claus ( **{ }** ), i els elements que contindran van separats per comes i seran parelles clau-valor de qualsevol tipus (fins i tot altres documents).

{ x : { a : 1 , b : 2 } }

Posar documents dins d'uns altres documents (el que s'anomena *embedded* *document*) ens permet guardar la informació d'una manera més real, no tan plana. Així per exemple, les dades d'una persona les podríem definir de la següent manera. Les posarem en una variable, per veure després com podem accedir als diferents elements, encara que el més normal serà guardar-lo en la Base de Dades (amb **insert()** o **save()** ). Si copiem el que va a continuació al terminal de Mongo, ens apareixerà amb un format estrany. És perquè la sentència d'assignació a la variable ocupa més d'una línia, i apareixeran 3 punts al principi per a indicar que continua la sentència. Però funcionarà perfectament :

doc = {
`    `nom:"Joan Martí",
`    `adreça: {
`        `carrer:"Major",
`        `número:1,
`        `població:"Castelló"
`    `} ,
`    `telèfons : [964223344,678345123]
}

Observeu com aquesta estructura que ha quedat tan clara, segurament en una Base de Dades Relacional ens hauria tocat guardar en 3 taules: la de persones, la d'adreces i la de telèfons.

Per a accedir als elements d'un document posàvem el punt. Doncs el mateix per als elements d'un document dins d'un document. I també podem accedir als elements d'un array, posant l'índex entre claudàtors.

\> doc.nom
Joan Martí

\> doc.adreça
{ "carrer" : "Major", "número" : 1, "població" : "Castelló" }

\> doc.adreça.carrer
Major

\> doc.telèfons
[ 964223344, 678345123 ]

\> doc.telèfons[0]
964223344

OBJECT ID

És un tipus que defineix MongoDB per a poder obtenir valors únics. És el valor per defecte de l'element **\_id** , necessari en tot document (atenció: en un document, no en un element de tipus document que hem dit equivalent a l'objecte de JSON). És un número long, és a dir que utilitza 24 bytes.

Farem proves de la seua utilització en la seüent pregunta, en el moment d'inserir diferents documents.

[« Anterior](33__utilitzaci_de_mongodb.md) | [Següent »](332__operacions_bsiques.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
