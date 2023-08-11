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

[« Anterior](31__estructura_json.md) | [Següent »](321__connexi_al_servidor_de_linstitut.md)
# <a name="main"></a>**3.2 - Instal·lació de MongoDB**
Podrem instal·lar MongoDB en qualsevol plataforma. I fins i tot sense tenir permisos d'administrador, com veurem en el cas d'Ubuntu.

Instal·lació en Linux

Per a poder fer la instal·lació més bàsica, podrem fer-lo sense permisos d'administrador. Si els tenim tot és més còmode, però si no en tenim també ho podem fer, com veurem i remarcarem a continuació.

De la pàgina de MongoDB ([**https://www.mongodb.com/download-center#community**](https://www.mongodb.com/download-center#community)) el més còmode és anar a la versió Community, i triar l'opció de la dreta [**Current releases & packages**](https://www.mongodb.com/download-center/community/releases), i ens baixem la versió apropiada per al nostre Sistema Operatiu. Observeu com en el cas de Linux hi ha moltes versions. En el cas d'**Ubuntu 20.04 de 64 bits**, aquest fitxer és: <https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-ubuntu2004-5.0.5.tgz>. Però recordeu que us heu d'assegurar de la versió

Senzillament descomprimirem aquest fitxer on vulguem, i ja estarà feta la instal·lació bàsica.

Per defecte el directori de la Base de Dades és **/data/db**

L'únic problema que podríem tenir si no som administradors és que no tinguem permís per crear aquest directori. Aleshores crearem un altre directori i en el moment d'arrancar el servidor, li especificarem aquest lloc.

La manera d'arrancar el servidor serà:

<directori arrel MongoDB>/bin/mongod

Opcionalment li podem dir on està la Base de Dades (si no ho especifiquem assumirà que està en **/data/db**):

<directori arrel MongoDB>/bin/mongod --dbpath <directori de la BD>

Resumint, i estant situats al directori on hem descomprimit MongoDB:

- Si som administradors: 
  - Creem el directori de dades:

mkdir /data
mkdir /data/db

- Arranquem el servidor:

./bin/mongod

- Si no som administradors: 
  - Creem el directori de dades:

mkdir data
mkdir data/db

- Arranquem el servidor:

./bin/mongod --dbpath ./data/db

La següent imatge il·lustra aquesta segona opció:

![ref1]

Una vegada en marxa el servidor, no hem de tancar aquesta terminal, ja que pararíem el servidor. Per a connectar un client, obrim una segona terminal i executem el client **mongo**:

./bin/mongo

![ref1]

Per a provar el seu funcionament, anem a fer un parell de comandos: un per a guardar un document i un altre per a reculerar-lo.

Per a qualsevol operació s'ha de posar **db** seguit del nom de la col·lecció, i després l'operació que volem fer. Amb el sgüent:

\> db.exemple.save( {msg:"Hola, què tal?"} )

Ens contestarà:

WriteResult({ "nInserted" : 1 })

Indicant que ha inserit un document en la col·lecció **exemple** (si no estava creada, la crearà).

I amb el següent comando recuperem la informació:

\> db.exemple.findOne()

Que ens tornarà:

{ "\_id" : ObjectId("56cc130590d651d45ef3d3be"), "msg" : "Hola, què tal?" }

Tot ho fa en la mateixa terminal, i a cadascú de nosaltres ens donarà un número diferent en **ObjectId**. En la següent imatge es veuen les dues operacions:

![ref2]

En realitat estem connectats a una Base de Dades anomenada **test**. Podem crear i utilitzar més d'una Base de Dades, però en aquest curs tindrés més que suficient amb aquesta Base de Dades. Per a comprovar-ho podem executar la següent sentència, que ens torna el nom de la Base de Dades:

\> db.getName()
test

Instal·lació en Windows

No ofereix cap dificultat. Ens baixem la versió apropiada de MongoDB per a Windows, depenent de si és de 32 o 64 bits la nostra versió, que resultarà ser un .msi directament executable. En el moment de fer aquestos apunts, el de la versió de 64 bits era el fitxer:

[mongodb-win32-x86_64-2008plus-ssl-3.2.3-signed.msi](https://www.mongodb.org/dr/fastdl.mongodb.org/win32/mongodb-win32-x86_64-2008plus-ssl-3.2.3-signed.msi/download)

Una vegada baixat, executem el fitxer. Haurem d'acceptar la llicència, instal·lar la versió completa, i acceptar quan Windows ens avise que un programa vol instal·lar software. El de sempre.

Com en el cas de Linux, abans d'executar el servidor haurem de tenir el directori creat. Per defecte el directori serà **\data\db**

Aqueste serien les ordres per a crear el directori i després arrancar el servidor:

mkdir \data\db
C:\Program Files\MongoDB\Server\3.2\bin\mongod.exe

En aquest a imatge s'observa que en intentar posar en marxa el servidor, el Firewall de Windows ho detecta, i sol·licita permés per posar-lo en marxa. Acceptem i prou:

![ref1]

Per a connectar-nos com a clients, ho haurem de fer des d'una altra terminal, ja que si tanquem aquesta pararem el servidor. El programa és **mongo.exe**:

C:\Program Files\MongoDB\Server\3.2\bin\mongo.exe

![ref3]

Per a provar el seu funcionament, anem a fer un parell de comandos: un per a guardar un document i un altre per a reculerar-lo.

Per a qualsevol operació s'ha de posar **db** seguit del nom de la col·lecció, i després l'operació que volem fer. Amb el sgüent:

\> db.exemple.save( {msg:"Hola, què tal?"} )

Ens contestarà:

WriteResult({ "nInserted" : 1 })

Indicant que ha inserit un document en la col·lecció **exemple** (si no estava creada, la crearà).

I amb el següent comando recuperem la informació:

\> db.exemple.findOne()

Que ens tornarà:

{ "\_id" : ObjectId("56cc1acd73b559230de8f71b"), "msg" : "Hola, què tal?" }

Tot ho fa en la mateixa terminal, i a cadascú de nosaltres ens donarà un número diferent en **ObjectId**. En la següent imatge es veuen les dues operacions:

![ref1]

En realitat estem connectats a una Base de Dades anomenada **test**. Podem crear i utilitzar més d'una Base de Dades, però en aquest curs tindrés més que suficient amb aquesta Base de Dades. Per a comprovar-ho podem executar la següent sentència, que ens torna el nom de la Base de Dades:

\> db.getName()
test

[« Anterior](31__estructura_json.md) | [Següent »](321__connexi_al_servidor_de_linstitut.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 32__installaci_de_mongodb.002.png
[ref2]: 32__installaci_de_mongodb.003.png
[ref3]: 32__installaci_de_mongodb.004.png
