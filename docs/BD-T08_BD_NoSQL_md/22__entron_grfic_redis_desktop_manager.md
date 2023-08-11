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

[« Anterior](21__installaci_de_redis.md) | [Següent »](23__utilitzaci_de_redis.md)
# <a name="main"></a>**2.2 - Entron gràfic: Redis Desktop Manager**
Com hem comprovat en el punt anterior, la connexió que fem des del client és a través de consola. Per tant haurem de posar comandos i ens contestarà la seua execució.

Podem instal·lar-nos una aplicació gràfica que faça un poc més atractiva la presentació.

La instal·lació d'aquesta eina és **totalment optativa**, no cal que la feu. De fet, ens els exemples que es mostraran en tot el tema només s'utilitzarà el mode consola.

És completament independent del servidor, i podem instal·lar-la perfectament sense tenir el servidor, utilitzant-la aleshores per a connectar a un servidor remot.

El podem baixar lliurement de la pàgina oficial [redisdesktop.com](redisdesktop.com) on podrem comprovar que tenim per a totes les plataformes:

![ref1]

Instal·lació en Ubuntu

Ens baixarem el paquet que haurem d'instal·lar bé amb el Centre de programari d'Ubuntu, o bé senzillament des d'una terminal, situats al directori on l'hem baixat fent

sudo dkpg -i redis-desktop-manager\_0.8.3-120\_amd64.deb

Com veieu fan falta permisos d'administrador, i si no hi ha problemes de dependències, s'instal·larà sense problemes.

Com que és igual que en Windows, si teniu curiositat mireu la imatge posterior de quan està instal·lat, per a comprovar la connexió al servior.

Instal·lació en Windows

En Windows el que ens baixarem és un exe. L'executem (permetent l'execució quan ho pregunta Windows) i li podem donar a totes les opcions per defecte.

Quan l'executem, ens eixirà la següent pantalla:

![ref1]

Podem comprovar que baix tenim el botó per a connectar a un servidor. Per a connectar al servidor local li posem com a adreça **localhost**. En la imatge s'ha fet el test de connexió.

![ref1]

Per a connectar a un remot, posarem la seua adreça:

![ref2]

En aquesta imatge es veu com hem connectat perfectament als dos servidors. Es pot comprovar com en cadascun d'ells hi ha més d'una Base de Dades, però nosaltres només utilitzarem la db0, que és a la que es connecta per defecte.

![ref3]

[« Anterior](21__installaci_de_redis.md) | [Següent »](23__utilitzaci_de_redis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 22__entron_grfic_redis_desktop_manager.002.png
[ref2]: 22__entron_grfic_redis_desktop_manager.003.png
[ref3]: 22__entron_grfic_redis_desktop_manager.004.png
