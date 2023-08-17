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

[« Anterior](53__cloud_firestore_cf.md) | [Següent »](exercicis.md)
# <a name="main"></a>**5.4 - Cloud Storage**
Cloud Storage ens permet guardar fitxers còmodament: fotos, vídeos, audios, ...

Combinat amb Reltime Database o Cloud Firestore ens permet guardar les nostres dedes de forma eficient, ja que podem guardar en les primeres les referències als fitxers que pugem al Storage.

L'entorn que ens ofereix Firebase per a gestionar Cloud Storage és molt senzill i no té cap secret, ja que ens permetrà pujar els fitxers, organitzant-los en subdirectoris, i també esborrar-los. En principi no necessitem més.

![ref1]

Si punxem en un fitxer podrem veure les seues característiques, i si el seleccionem podrem esborrar-lo o obrir-lo en una altra finestra.

![ref2]

Aquest entorn, de tan senzill, fins i tot es queda un poc curt, ja que no ens permetrà canviar el nom d'un fitxer, o moure'l a una carpeta, ...

Si vulguérem fer algun canvi d'aquestos, canviar el nom o canviar de carpeta, ho hauríem de fer des d'un altre lloc, un altre navegador del Google Cloud Storage (<https://console.cloud.google.com/storage/browser>):

![ref3]

on es pot observar com en els 3 puntets de la dreta d'un fitxer ens apareixen moltes opcions com copiar, menejar, renomenar, ...

Però nosaltres en principi tindrem prou amb la primera consola. Anem alerta de col·locar les coses al lloc, i si no estan, esborrem i col·loquem al lloc correcte.

Ja que estem en la consola, controlem els permisos (**Rules**) en la pestanya corresponent de la consola:

![ref4]

En aquesta imatge s'aprecia que no hi haurà permís per a llegir ni escriure fora de la consola. Com que el que volem és accedir des de les aplicacions d'Eclipse i d'Android, substituirem el permís per aquest:

allow read, write: if request.time < timestamp.date(2023, 6, 30);

![ref5]

amb una data en la qual no ens pillem els dits.

**Nota**

Observeu com tant en la consola senzilla com en la del browser de GoogleCloud, ens posa una adreça, que en el meu cas és: **gs://acces-a-dades-6e5a6.appspot.com**. Es tracta de l'adreça del **bucket** (poal, contenidor) on estan col·locats els fitxers. Podem crear més **buckets**, però no ho complicarem. Haurem de tenir clara la referència a aquest bucket per defecte.

[« Anterior](53__cloud_firestore_cf.md) | [Següent »](exercicis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 54__cloud_storage.002.png
[ref2]: 54__cloud_storage.003.png
[ref3]: 54__cloud_storage.004.png
[ref4]: 54__cloud_storage.005.png
[ref5]: 54__cloud_storage.006.png
