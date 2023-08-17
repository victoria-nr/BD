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

[« Anterior](342__operadors_de_les_condicions.md) | [Següent »](4__bd_xml_existdb.md)
# <a name="main"></a>**3.4.3 - Agregació**
L'agregació ens permetrà fer consultes molt avançades. És un procés un poc complicat però molt potent. Ens donarà una potència quasi com la del SQL quan comencem a utilitzar el GROUP BY i HAVING.

La tècnica que s'utilitza és la del ***pipeline***, és a dir fer una sèrie de comandos, cadascun agafa les dades que proporciona l'anterior i a la seua vegada proporciona les dades al següent comando. D'aquesta manera es tractarà un conjunt de documents i es faran "operacions" sobre ells seqüencialment en blocs: filtrat, projecció, agrupacions, ordenació, limitació i *skipping* (saltar alguns).

La sintaxi serà:

db.col\_leccio1.aggregate ( *operador $matc*h , *operador $projec*t , *operador $group* , *operador $sort* , *operador $limit* , *operador $skip* )

L'ordre dels operadors pot canviar, però hem de tenir en compte que els comandos s'executen en el ordre en què els posem (d'esquerra a dreta). Així, per exemple, pot ser molt convenient posar el primer operador el $match, que és el de seleccionar documents, així les altres operacions es faran sobre menys documents i aniran més ràpides.

Cada paràmetre del aggregate, és a dir, cada operador tindrà format JSON, i per tant sempre serà de l'estil:

{ $operador : { clau:valor , ... } }

Operador $match

Servirà per a filtrar els documents. Aleshores, l'agregació només afectarà als documents seleccionats. Es poden utilitzar tots els operadors que hem anat estudiant.

El següent exemple selecciona (per a aggregate, però com no fem res més senzillament selecciona els documents) els documents de l'editorial Planeta.

\> db.libro.aggregate({$match:{editorial:"Planeta"}})

En el següent exemple, a més de seleccionar els de l'editorial Planeta després apliquem una projecció sobre els camps títol i editorial, per a poder visualitzar millor el resultat.

\> db.libro.aggregate({$match:{editorial:"Planeta"}},{$project:{titulo:1,editorial:1}})
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "editorial" : "Planeta" }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "editorial" : "Planeta" }

Operador $project

Ens permet projectar sobre determinats camps del document, però és molt més complet que en la projecció "normal" que havíem fet fins ara, ja que permet també renomenar camps, fer càlculs, etc.

**Projecció**

La manera més senzilla, evidentment és projectar sobre alguns camps dels existents, i el funcionament és idèntic al de l'altra vegada (valors 1 per a que apareguen, 0 per a que no apareguen; per defecte **\_id** sempre apareix):

\> db.libro.aggregate({$project:{titulo:1,editorial:1}})
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "editorial" : "Planeta" }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "editorial" : "Plaza & Janes" }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "editorial" : "Gigamesh" }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "editorial" : "Debolsillo" }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "editorial" : "Embolsillo" }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "editorial" : "Planeta" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

**Renomenar**

$project també ens permet renomenar camps existents (després veurem que també càlculs). La manera serà posar d'aquest manera:

{ $project : { "nom\_nou" : "$camp\_vell" } }

El secret està en el dòlar que va davant del camp vell, ja que d'aquesta manera ens referim al valor d'aquest camp. Així per exemple renomenem el camp **enstock** a **disponible**, a banda de traure el títol:

\> db.libro.aggregate({$project:{titulo:1 , disponible:"$enstock"}})
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "disponible" : true }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "disponible" : true }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "disponible" : true }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "disponible" : false }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "disponible" : true }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "disponible" : false }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "disponible" : true }

**Camps calculats**

Amb aquest nom genèric ens referirem a tots els càlculs, expressions i més coses que podrem posar per a transformar el que ja tenim. Com veiem, açò és molt més potent que la projecció normal.

- **Expressions matemàtiques**: Podrem aplicar fórmules per a sumar (**$add**), restar (**$subtract**), multiplicar (**$multiply**), dividir (**$divide**) i més coses (potència, arrel quadrada, valor absolut, mòdul, ...). Cada operació té el seu operador que serà una paraula precedida pel dòlar, i amb la sintaxi de JSON, on posarem els operands en un array. 

Per exemple, traurem títol del llibre, preu i preu en pessetes (multiplicant per 166.386)

\> db.libro.aggregate({$project:{titulo:1 , precio:1 , preu\_pessetes:{$multiply:["$precio" , 166.386]}}})
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "precio" : 21.75, "preu\_pessetes" : 3618.8955 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "precio" : 21.75, "preu\_pessetes" : 3618.8955 }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "precio" : 9.5, "preu\_pessetes" : 1580.667 }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "precio" : 9.45, "preu\_pessetes" : 1572.3476999999998 }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "precio" : 11, "preu\_pessetes" : 1830.2459999999999 }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "precio" : 17.23, "preu\_pessetes" : 2866.83078 }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "precio" : 15.9, "preu\_pessetes" : 2645.5374 }

- **Expressions de dates**: Ja veurem i ja podem anar intuint que moltes agregacions estaran basades en el temps, per a poder fer consultes de documents de la setmana passada, o el mes passat, ... Per a poder fer aquestes agregacions, hi ha un conjunt d'expressions que permeten extraure fàcilment d'una data el seu dia, mes, any, ... en forma de número

Són les expressions: **$year, $month, $week, $dayOfMonth, $DayOfWeek, $dayOfYear, $hour, $minute** i **$second**.

En el següent exemple traurem tots els documents, projectant per la data, any i mes:

\> db.libro.aggregate({$project : {fecha:1 , año:{$year:"$fecha"} , mes:{$month:"$fecha"}}})
{ "\_id" : "9788408117117", "fecha" : ISODate("2013-08-29T00:00:00Z"), "año" : 2013, "mes" : 8 }
{ "\_id" : "9788401342158", "fecha" : ISODate("2014-03-01T00:00:00Z"), "año" : 2014, "mes" : 3 }
{ "\_id" : "9788496208919", "fecha" : ISODate("2011-11-24T00:00:00Z"), "año" : 2011, "mes" : 11 }
{ "\_id" : "9788499088075", "fecha" : ISODate("2009-01-09T00:00:00Z"), "año" : 2009, "mes" : 1 }
{ "\_id" : "9788415140054", "fecha" : ISODate("2012-10-30T00:00:00Z"), "año" : 2012, "mes" : 10 }
{ "\_id" : "9788408113331", "fecha" : ISODate("2013-06-04T00:00:00Z"), "año" : 2013, "mes" : 6 }
{ "\_id" : "9788468738895", "fecha" : ISODate("2014-02-06T00:00:00Z"), "año" : 2014, "mes" : 2 }

- **Expressions de strings**: Ens permeten manipular els strings per a extraure subcadenes, concatenar, passar a majúscules o minúscules. Aquestes són algunes de les funcions:
  - **$substr : [exp , inici , llargària]** : extrau una subcadena del string del primer paràmetre, des de la posició que indica el segon paràmetre (o primer caràcter) i tants caràcters com el tercer paràmetre
  - **$concat : [ exp1 , exp2 , ...]** : concatena les expressions que hi ha en l'array
  - **$toLower : exp** i **$toUpper : exp** : converteixen l'expressió a majúscules i minúscules respectivament

Per exemple, anem a traure el títol dels llibres amb l'autor entre parèntesis:

\> db.libro.aggregate({$project: { "Llibre:" : {$concat : ["$titulo" , " (" , "$autor" , ")"]}}})
{ "\_id" : "9788408117117", "Llibre:" : "Circo Máximo (Santiago Posteguillo)" }
{ "\_id" : "9788401342158", "Llibre:" : "El juego de Ripper (Isabel Allende)" }
{ "\_id" : "9788496208919", "Llibre:" : "Juego de tronos: Canción de hielo y fuego 1 (George R.R. Martin)" }
{ "\_id" : "9788499088075", "Llibre:" : "La ladrona de libros (Markus Zusak)" }
{ "\_id" : "9788415140054", "Llibre:" : "La princesa de hielo (Camilla Lackberg)" }
{ "\_id" : "9788408113331", "Llibre:" : "Las carreras de Escorpio (Maggie Stiefvater)" }
{ "\_id" : "9788468738895", "Llibre:" : "Las reglas del juego (Anna Casanovas)" }

I ara el mateix, però amb el títol en majúscules:

\> db.libro.aggregate({$project: { "Llibre:" : {$concat : [{$toUpper:"$titulo"}, " (" , "$autor" , ")"]}}})
{ "\_id" : "9788408117117", "Llibre:" : "CIRCO MáXIMO (Santiago Posteguillo)" }
{ "\_id" : "9788401342158", "Llibre:" : "EL JUEGO DE RIPPER (Isabel Allende)" }
{ "\_id" : "9788496208919", "Llibre:" : "JUEGO DE TRONOS: CANCIóN DE HIELO Y FUEGO 1 (George R.R. Martin)" }
{ "\_id" : "9788499088075", "Llibre:" : "LA LADRONA DE LIBROS (Markus Zusak)" }
{ "\_id" : "9788415140054", "Llibre:" : "LA PRINCESA DE HIELO (Camilla Lackberg)" }
{ "\_id" : "9788408113331", "Llibre:" : "LAS CARRERAS DE ESCORPIO (Maggie Stiefvater)" }
{ "\_id" : "9788468738895", "Llibre:" : "LAS REGLAS DEL JUEGO (Anna Casanovas)" }

Operador $group

Realitza grups sobre els documents seleccionats prèviament, per a valors iguals del camp o expressions que determinem. Posteriorment, amb els grups, podrem realitzar operacions, com sumar o traure la mitjana d'alguna quantitat dels documents del grup, o el màxim o mínim, ...

Per a poder agrupar, haurem de definir com a **\_id** del grup el camp o camps pels valors dels quals volem agrupar. Per exemple, si volem agrupar els llibres per l'editorial, haurem de definir el **\_id** del grup el camp editorial

$group : { "\_id" : *camp o camps* }

Si agrupem per un únic camp, senzillament el posem amb un dòlar davant i entre cometes. Si és més d'un camp, els posem com un objecte. Per exemple, agrupem per editorial:

\> db.libro.aggregate( { $group : { "\_id" : "$editorial" } } )
{ "\_id" : "Debolsillo" }
{ "\_id" : null }
{ "\_id" : "Gigamesh" }
{ "\_id" : "Embolsillo" }
{ "\_id" : "Plaza & Janes" }
{ "\_id" : "Planeta" }

Podem observar com hi ha algun llibre que no té editorial.

Ara agrupem per any de publicació (l'extraurem del camp **fecha**):

\> db.libro.aggregate( { $group : { "\_id" : { "any" : { $year : "$fecha" } } } } )
{ "\_id" : { "any" : 2012 } }
{ "\_id" : { "any" : 2009 } }
{ "\_id" : { "any" : 2011 } }
{ "\_id" : { "any" : 2014 } }
{ "\_id" : { "any" : 2013 } }

I ara agrupem per editorial i any de publicació (els dos llibres de Planeta són del 2013)

\> db.libro.aggregate( { $group : { "\_id" : { "Editorial" : "$editorial" , "any" : { $year : "$fecha" } } } } )
{ "\_id" : { "Editorial" : "Embolsillo", "any" : 2012 } }
{ "\_id" : { "any" : 2014 } }
{ "\_id" : { "Editorial" : "Debolsillo", "any" : 2009 } }
{ "\_id" : { "Editorial" : "Gigamesh", "any" : 2011 } }
{ "\_id" : { "Editorial" : "Plaza & Janes", "any" : 2014 } }
{ "\_id" : { "Editorial" : "Planeta", "any" : 2013 } }

**Operadors d'agrupació**

Ens permetran fer alguna operació sobre els documents del grup. Es posen com a segon paràmetre del grup (després de la definició del **\_id**).

- **$sum : valor** : sumarà el valor de tots els documents del grup. El valor pot ser un camp numèric, o alguna altra cosa més complicada.
- **$avg : valor** : calcularà la mitjana dels valors per als documents del grup
- **$max : valor** : màxim
- **$min : valor** : mínim
- **$first : exp** : agafarà el primer valor de l'expressió del grup, ignorant les altres del grup
- **$last : exp** : agafarà l'últim

Per exemple, la suma dels preus dels llibres de cada editorial:

\> db.libro.aggregate( { $group : { "\_id" : "$editorial" , "suma\_preus" : { $sum : "$precio"} } } )
{ "\_id" : "Debolsillo", "suma\_preus" : 9.45 }
{ "\_id" : null, "suma\_preus" : 15.9 }
{ "\_id" : "Gigamesh", "suma\_preus" : 9.5 }
{ "\_id" : "Embolsillo", "suma\_preus" : 11 }
{ "\_id" : "Plaza & Janes", "suma\_preus" : 21.75 }
{ "\_id" : "Planeta", "suma\_preus" : 38.980000000000004 }

O la mitjana dels preus de cada any:

\> db.libro.aggregate( { $group : { "\_id" : { "any" : { $year : "$fecha" } } , "mitjana preus" : { $avg : "$precio" } } } )
{ "\_id" : { "any" : 2012 }, "mitjana preus" : 11 }
{ "\_id" : { "any" : 2009 }, "mitjana preus" : 9.45 }
{ "\_id" : { "any" : 2011 }, "mitjana preus" : 9.5 }
{ "\_id" : { "any" : 2014 }, "mitjana preus" : 18.825 }
{ "\_id" : { "any" : 2013 }, "mitjana preus" : 19.490000000000002 }

Operador $sort

Serveix per a ordenar i segueix la mateixa sintàxi que en les consultes normal (1: ordre ascendent; -1: ordre descendent). Podrem ordenar pels camps normals o per camps clalculats.

Per exemple ordenem per la suma de preus de cada editorial:

\> db.libro.aggregate( { $group : { "\_id" : "$editorial" , "suma\_preus" : { $sum : "$precio"} } } , { $sort : { suma\_preus : 1 } })
{ "\_id" : "Debolsillo", "suma\_preus" : 9.45 }
{ "\_id" : "Gigamesh", "suma\_preus" : 9.5 }
{ "\_id" : "Embolsillo", "suma\_preus" : 11 }
{ "\_id" : null, "suma\_preus" : 15.9 }
{ "\_id" : "Plaza & Janes", "suma\_preus" : 21.75 }
{ "\_id" : "Planeta", "suma\_preus" : 38.980000000000004 }

I ara ordenem de forma descendent per la mitjana de preus de cada any:

\> db.libro.aggregate( { $group : { "\_id" : {"any":{$year:"$fecha"}} , "mitjana preus":{$avg:"$precio"} } } , {$sort:{"mitjana preus":-1}})
{ "\_id" : { "any" : 2013 }, "mitjana preus" : 19.490000000000002 }
{ "\_id" : { "any" : 2014 }, "mitjana preus" : 18.825 }
{ "\_id" : { "any" : 2012 }, "mitjana preus" : 11 }
{ "\_id" : { "any" : 2011 }, "mitjana preus" : 9.5 }
{ "\_id" : { "any" : 2009 }, "mitjana preus" : 9.45 }

Operador $limit

Limita el resultat del aggregate al número indicat.

Per exemple, els tres anys de mitjana de preus més cara. És com l'últim exemple, afegint el límit:

\> db.libro.aggregate({$group:{"\_id":{"any":{$year:"$fecha"}},"mitjana preus":{$avg:"$precio"}}} , {$sort:{"mitjana preus":-1}} , {$limit:3})
{ "\_id" : { "any" : 2013 }, "mitjana preus" : 19.490000000000002 }
{ "\_id" : { "any" : 2014 }, "mitjana preus" : 18.825 }
{ "\_id" : { "any" : 2012 }, "mitjana preus" : 11 }

Operador $skip

Salta el número indicat

En l'exemple anterior, ara saltem els 3 primers:

\> db.libro.aggregate({$group:{"\_id":{"any":{$year:"$fecha"}},"mitjana preus":{$avg:"$precio"}}} , {$sort:{"mitjana preus":-1}} , {$skip:3})
{ "\_id" : { "any" : 2011 }, "mitjana preus" : 9.5 }
{ "\_id" : { "any" : 2009 }, "mitjana preus" : 9.45 }

[« Anterior](342__operadors_de_les_condicions.md) | [Següent »](4__bd_xml_existdb.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
