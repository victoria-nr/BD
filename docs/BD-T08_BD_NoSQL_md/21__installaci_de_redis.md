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

[« Anterior](2__bd_clauvalor_redis.md) | [Següent »](22__entron_grfic_redis_desktop_manager.md)
# <a name="main"></a>**2.1 - Instal·lació de Redis**
Redis està construït per a Linux. També funciona, però, des de Windows com veurem una miqueta més avant.

Instal·lació en Linux

El lloc des d'on baixar-lo és la pàgina oficial:

<http://redis.io>

En el moment de fer aquestos apunts, l'última versió estable és la **6.2.6**.

Ens baixem el fitxer, el descomprimim, i després des d'una terminal ens situem en el directori on s'ha descomprimit i fem **make** per a generar els executables. Després de molts avisos, s'hauria d'haver instal·lat bé, i sense ser necessaris els permisos d'administrador. Aquest seria el resum d'accions, fetes totes elles des d'una terminal (però no cal descomprimir des d'una terminal) i havent-nos situat prèviament en el lloc on està el fitxer baixat. També suposarem que el fitxer està col·locat en el lloc on volem que estiga instal·lat de forma definitiva. Recordeu que podeu descomprimir-lo de la manera que us resulte més còmoda:

tar xzf redis-6.2.6.tar.gz

o també el podeu descomprimir des del navegador d'arxius, com ja havíem comentat.

Una vegada descomprimit, des d'una terminal ens hem de situar en el directori acabat de descomprimir i fer **make**

cd redis-6.2.6

make

Amb açò s'haurien d'haver generat els executables, i ja hauria de funcionar. Recordeu que no fan falta permisos d'administrador per a realitzar açò.

Per a posar en marxa el servidor, quasi que el més còmode serà obrir un terminal, situar-nos en el directori **redis-6.2.6/src** i des d'ahi executar **redis-server**. Hauria d'eixir una finestra similar a la següent, amb més o menys avisos (observeu que al principi de la imatge estan les ordres donades).

`  `![ref1]

Entre altres coses diu que el servidor està en marxa esperant connexions al port 6379, que és el port per defecte de Redis. Aquesta finestra del terminal l'haurem de deixar en marxa. Quan vulguem detenir Redis, senzillament fem **ctrl-c**, i detindrem l'execució de forma ordenada (guardant-se les dades no guardades i tancant-se tot bé)

Podríem haver executat directament **redis-server** fent-li doble-clic des d'un explorador d'arxius, per exemple, però aleshores no podríem parar-lo i en definitiva controlar-lo tan còmodament.

Per a fer una connexió des d'un client, també des d'un terminal (un altre) executem **redis-cli**:

![ref2]

Ja ha fet la connexió, concretament a localhost (127.0.0.1) i al port 6379, que havíem quedat que és el port per defecte.

Comprovem que sí que funciona. Encara no hi ha dades, perquè l'acabem d'instal·lar. I recordeu que és una Base de Dades clau-valor. Per a crear una entrada posarem **set clau valor**. Per a obtenir-la posarem **get clau**. En la imatge es pot comprovar:

![ref3]

Hem creat una clau anomenada **clau\_1** amb el valor **primera**, com es pot comprovar en el moment d'obtenir-la amb **get**.

Si al programa **redis-cli** no li posem paràmetres, intentarà fer una connexió local (localhost). Si volem connectar a un servidor situat en una altra adreça, li la posem amb el paràmetre **-h adreça**, per exemple:

redis-cli -h 192.168.1.26

Ací tenim una imatge des d'una connexió externa, des d'un altre equip:

![ref4]

**Nota: Connexió al servidor de l'Institut**

En el servidor de dades de l'Institut també tenim instal·lat redis. Però per a no tenir accessos no desitjats, cal una autenticació. Senzillament és posar el comando auth amb la contrasenya: **auth ieselcaminas.ad**

En la següent imatge es veu com sí que hem pogut connectar

![ref5]

Instal·lació en Windows de 64 bits

Encara que Redis està construït per a Linux, hi ha versions per a Windows, preferiblement de 64 bits. També podrem trobar versions de 32 bits, però molt més antigues.

El lloc on poder baixar els fitxers de Redis per a Windows de 64 bits és:

https://github.com/MSOpenTech/redis/releases



![ref6]

Ens baixem el **zip**, el descomprimim, i ja ho tindrem disponible (sense fer **make** ni res). Observeu com en la carpeta resultat de descomprimir ja tenim els executables **redis-server** i **redis-cli** que són els que ens interessen:

![ref7]

Executem **redis-server** directament i ja el tindrem en marxa:

![ref8]

Executem també el **redis-cli** i el resultat serà el mateix que en Linux. Hem incorporar una nova clau i després obtenim el seu contingut:

![ref9]

Instal·lació en Windows de 32 bits

És un poc més complicada de trobar. I sobretot, és una versió prou més antiga. Podem descarregar-la de la següent adreça:

<https://github.com/rgl/redis/downloads>

![ref10]

Aquesta sí que és d'instal·lació (no de descompressió únicament). La documentació suggereix que s'active com un servei. Per això, en la llista de programes de l'Inici no està el server, únicament el **client**. Però el podem trobar en el directori on s'ha instal·lat: **C:\Archivos de programa\Redis**. Trobarem tant **redis-server.exe** com **redis-cli.exe**. Posem en marxa el servidor fent doble-clic a **redis-server.exe**:

![ref11]

I ja només falta posar en marxa el client (des del menú o fent doble-clic a **redis-cli.exe**). En la imatge es veu com podem connectar, crear una clau i tornar el seu valor:

![ref12]

[« Anterior](2__bd_clauvalor_redis.md) | [Següent »](22__entron_grfic_redis_desktop_manager.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 21__installaci_de_redis.002.png
[ref2]: 21__installaci_de_redis.003.png
[ref3]: 21__installaci_de_redis.004.png
[ref4]: 21__installaci_de_redis.005.png
[ref5]: 21__installaci_de_redis.006.png
[ref6]: 21__installaci_de_redis.007.png
[ref7]: 21__installaci_de_redis.008.png
[ref8]: 21__installaci_de_redis.009.png
[ref9]: 21__installaci_de_redis.010.png
[ref10]: 21__installaci_de_redis.011.png
[ref11]: 21__installaci_de_redis.012.png
[ref12]: 21__installaci_de_redis.013.png
