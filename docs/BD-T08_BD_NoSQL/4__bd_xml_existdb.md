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

[« Anterior](343__agregaci.md) | [Següent »](41__installaci_dexistdb.md)
# <a name="main"></a>**4 - BD XML: eXist-db**
L’**XML** és, segons la definició feta pel World Wide Web Consortium (W3C), un format simple basat en text per a representar informació estructurada: documents, dades, configuracions, llibres, transaccions, factures i molt més. Va ser derivat d’un format estàndard més antic, anomenat SGML, amb la finalitat de ser més adequat per a la seua utilització en la web.

L’XML, avui en dia, és un dels formats més utilitzats per a l’**intercanvi** d’informació estructurada: entre els programes, entre les persones, entre ordinadors i persones, tant a nivell local com a través de les xarxes. El fet que la informació s’intercanvie en format XML ha implicat l’aparició de mecanismes que permeten enregistrar aquesta informació en format XML, de manera que no siga necessari efectuar traduccions a altres formats.

Les **Bases de Dades XML natives**, o senzillament **Bases de Dades XML** ens permetran guardar documents XML i són Bases de Dades centrades en els documents. La unitat mínima d'emmagatzematge és el document XML.

Podríem definir **SGBD-XML natives** com un sistema de gestió de la informació que ha de:

- Definir un model lògic per a un document XML (en contraposició als SGBD habilitats que defineixen el model per les dades) i enregistrar i recuperar els documents segons aquest model. Com a mínim, el model ha d’incloure elements, atributs, PCDATA i l’ordre del document.
- Mantenir una relació transparent amb el mecanisme subjacent d’emmagatzematge, incorporant les característiques ACID de qualsevol SGBD (*Atomicity, Consistency, Isolation and Durability*).
- Incloure un nombre arbitrari de nivells de dades i complexitat.
- Permetre les tecnologies de consulta i transformació pròpies d’XML: **XPath**, XSLT, XQL, **XQuery**, etc.

Avantatges de les BD-XML, en comparació a les BD no XML:

- Faciliten accés i emmagatzematge d’informació en format XML sense necessitat de codi addicional ni cap tipus de mapatge.
- La majoria d’SGBD-XML natives incorporen un motor de recerca d’alt rendiment.
- És molt senzill afegir nous documents XML.
- Permeten emmagatzemar dades heterogènies.
- Conserven la integritat dels documents (es poden recuperar en el seu estat inicial).

Per contra, els inconvenients que tenen normalment els SGBD-XML natives són aquestos:

- La gran quantitat d’espai necessari per emmagatzemar el mateix document XML com a format de representació de la informació, a causa del fet que les etiquetes poden suposar el 75% de la informació d’un document XML. I això és, sense cap mena de dubte, innecessari en guardar molts documents validats per un mateix XSD o DTD.
- El fet que les BD-XML natives només puguen guardar i retornar dades en format XML.
- En emmagatzemar la informació en format XML es fa molt complicat poder generar noves estructures a partir de la informació existent com, per exemple, aconseguir càlculs estadístics.
- Les dificultats d’indexació del contingut d’una base de dades, que ha de permetre la reducció dràstica del temps necessari per trobar certs elements clau.
- Les pobres facilitats per modificar el contingut dels documents XML emmagatzemats sense haver de substituir tot el document.

Els dos darrers inconvenients (indexació-actualització) són cavalls de batalla dels SGBD i de ben segur que s’anirà avançant en aquest camp fins que deixen de ser inconvenients. 

[« Anterior](343__agregaci.md) | [Següent »](41__installaci_dexistdb.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
