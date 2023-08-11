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

[« Anterior](4213__seqncies.md) | [Següent »](422__xquery.md)
# <a name="main"></a>**4.2.1.4 - Funcions**
XPath ofereix una gran quantitat de funcions destinades a manipular els resultats obtinguts.

Aquestes funcions es classifiquen en diferents grups:

- **Per manipular conjunts de nodes**: es pot obtenir el nom dels nodes, treballar amb les posicions, comptar-los, etc.
- **Per treballar amb cadenes de caràcters**: permeten extreure caràcters, concatenar, comparar… les cadenes de caràcters.
- **Per fer operacions numèriques**: es poden convertir els resultats a valors numèrics, comptar els nodes, fer operacions, etc.
- **Funcions booleanes**: permeten fer operacions booleanes amb els nodes.
- **Funcions per dates**: permeten fer operacions diverses amb dates i hores.

És impossible especificar-les totes en aquestos apunts, de manera que el millor és consultar l’especificació XPath ([http://www.w3.org/TR/xpath-functions](http://www.w3.org/TR/xpath-functions/ "http://www.w3.org/TR/xpath-functions/")) per veure quines funcions es poden fer servir.

Entre totes les funcions podem destacar les de la següent taula:

|**Funció**|**Explicació**|
| :-: | :-: |
|**name()**|Retorna el nom del node|
|**sum()**|Retorna la suma d’una seqüència de nodes o de valors|
|**count()**|Retorna el nombre de nodes que hi ha en una seqüència|
|**avg()**|Fa la mitjana dels valors de la seqüència|
|**max()**|Retorna el valor màxim de la seqüència|
|**min()**|Dóna el valor mínim de la seqüència|
|**position()**|Diu en quina posició es troba el node actual|
|**last()**|Retorna si el node actual és l’últim|
|**distinct-values()**|Retorna els elements de la seqüència sense duplicats|
|**concat()**|Uneix dues cadenes de caràcters|
|**starts-with()**|Retorna si la cadena comença amb els caràcters marcats|
|**contains()**|Ens diu si el resultat conté el valor|
|**string-length()**|Retorna la llargària de la cadena|
|**substring()**|Permet extraure una subcadena del resultat|
|**string-join()**|Uneix la seqüència amb el separador especificat|
|**current-date()**|Ens retornarà l’hora actual|
|**not()**|Inverteix el valors booleans|

Amb les funcions es podran fer peticions que retornen valors numèrics. Per exemple, “quants alumnes tenim?”: 

count(/classe/alumnes/alumne)

que tornarà el nombre d'alumnes del fitxer 

3

O bé retornar cadenes de caràcters. Per exemple, unir tots els noms, separant-los per una coma: 

string-join(/classe//nom,",")

que tornarà en un únic resultat els noms separats per una coma: 

"Joan,Albert,Bernat,Joan"

També es poden posar les funcions en les condicions. Per exemple, aquesta expressió ens tornarà els alumnes amb el cognom que comence per B: 

/classe/alumnes/alumne[starts-with(cognoms,"B")]

<alumne aprovat="no">
<nom>Bernat</nom>
<cognoms>Balaguer</cognoms>
<nota>3</nota>
</alumne>

En aquesta expressió volem obtenir el tercer alumne de la llista: 

/classe/alumnes/alumne[position()=3]

<alumne delegat="si" aprovat="si">
<nom>Joan</nom>
<cognoms>Centelles</cognoms>
<nota>8</nota>
</alumne>

[« Anterior](4213__seqncies.md) | [Següent »](422__xquery.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
