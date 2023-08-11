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

[« Anterior](4222__variables.md) | [Següent »](4224__expressions_flwor.md)
# <a name="main"></a>**4.2.2.3 - Expressions avaluables**
XQuery està pensat per poder mesclar les consultes amb qualsevol altre tipus de contingut. Si es mescla amb contingut, les expressions que s’hagen d’avaluar s’han de col·locar entre claus ”**{…}**”.

Per exemple, podem mesclar HTML i XQuery per tal que el processador XQuery genere una pàgina web amb les dades d’un document XML.

<html>

<head><title>Llista de classe</title></head>

<body>

<h1>

{

//assignatura

}

</h1>

</body>

</html>

<html>
`  `<head>
`    `<title>Llista de classe</title>
`  `</head>
`  `<body>
`    `<h1>
`      `<assignatura>Llenguatges de Marques</assignatura>
`    `</h1>
`  `</body>
</html>

En mesclar contingut, el processador XQuery només avaluarà les instruccions que estiguen dins de les claus, i per tant ha deixat les etiquetes HTML tal com estan.

Creació d'elements i atributs

Fent servir les expressions avaluables és fàcil crear nous elements.

<modul>

{  //assignatura/text() }

</modul>

<modul>Llenguatges de Marques</modul>

També es poden crear atributs (s’ha d’anar en compte de no deixar-se les cometes al voltant del valor que obtindran els atributs).

<modul nom="{ //assignatura/text() }"/>

<modul nom="Llenguatges de Marques"/>

Una manera alternativa i més potent de definir elements i atributs és fer servir les paraules clau **element** i **attribute**. Aquestes instruccions permeten crear elements i definir-ne el contingut especificant-lo dins de les claus.

element modul {

}

Crearia l'element buit **<modul/>**

Si volem crear nous elements o atributs dins d’un element definit d’aquesta manera s’han d’especificar dins de les claus. Per exemple, el codi següent:

element modul {

attribute nom { //assignatura/text()},

element alumnes { //alumne }

}

Que ens donarà el següent resultat:

<modul nom="Llenguatges de Marques"> 

<alumnes> 

<alumne aprovat="si"> 

<nom>Albert</nom>

<cognoms>Alegre</cognoms>

<nota>6</nota>

</alumne>

<alumne aprovat="no"> 

<nom>Bernat</nom>

<cognoms>Balaguer</cognoms>

<nota>3</nota>

</alumne>

<alumne delegat="si" aprovat="si"> 

<nom>Joan</nom>

<cognoms>Centelles</cognoms>

<nota>8</nota>

</alumne>

</alumnes>

</modul>



[« Anterior](4222__variables.md) | [Següent »](4224__expressions_flwor.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
