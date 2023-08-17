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

[« Anterior](54__cloud_storage.md)
# **Exercicis**
![ref1]
## **Exercici 8.1 (Redis)**
Sobre la Base de Dades **REDIS** del Servidor de l'Institut (adreça **89.36.214.106**) fer les següents operacions, tant per a guardar una sèrie de dades, com per a recuperar-les. Sempre posarem a les claus el prefix **9999x\_** , on com sempre heu de substituir 9999 per les 4 últimes xifres del vostre DNI, i la x per la letra del NIF. Copia-les en un únic fitxer de text, de forma numerada. És aquest fitxer el que hauràs de pujar.

1. Crea la clau **9999x\_Nom** amb el teu nom
1. Crea la clau **9999x\_Cognoms** amb els teus cognoms. Una de les dues almenys, nom o cognoms, ha de constar de més d'una paraula.
1. Mostra totes les claus teues, i únicament les teues.
1. Dóna un temps de vida a la clau **9999x\_Nom** de **200 segons**. Comprova el temps de vida que li queda. Posteriorment fes-la **permanent**.
1. Crea la clau **9999x\_Adreca**, de tipus Hash, amb els subcamps **carrer**, **numero** i **cp**. No importa que les dades siguen falses. Pots fer-lo en una sentència o en més d'una.
1. Afegeix a l'anterior el subcamp **poblacio**
1. Mostra tota la informació de la teua adreça (només la informació, no les subclaus)
1. Crea la clau **9999x\_Moduls\_ASIX** o **9999x\_Moduls\_DAM** o **9999x\_Moduls\_DAW**, depenent del teu cicle. Ha de ser de tipus Set, amb tots els mòduls del teu cicle, que es detallen a continuació. Pots fer-lo en una o en més d'una sentència. 
   1. **ASIX**: ISO, PAX, FH, GBD, LM, FOL, ASO, SXI, IAW, ASGBD, SAD, EIE, PROJ i FCT
   1. **DAW**: SI, BD, PR, LM, ED, FOL, DWEC, DWES, DAW, DIW, EIE, PROJ i FCT
   1. **DAM**: SI, BD, PR, LM, ED, FOL, AD, PMDM, DI, PSP, SGE, EIE, PROJ i FCT.
1. Crea la clau **9999x\_Moduls\_meus**, de tipus Set, amb tots els mòduls als quals estàs matriculat. Pots fer-lo en una o en més d'una sentència.
1. Guarda en la clau **9999x\_Moduls\_altres** els mòduls en els quals no estàs matriculat actualment. Ha de ser per mig d'operacions de conjunts. Pots comprovar que el resultat és correcte amb **smembers**
1. Crea una llista amb el nom **9999x\_Notes\_BD** amb la nota de 4 exercicis de BD. Les notes seran: 7, 9, 6, 10. Han de quedar en aquest ordre (no en ordre invers)
1. Modifica la tercera nota, que passa de ser 6 a 8.
1. Crea un **Set Ordenat** (**zset**) anomenat **9999x\_Carrera** amb els següents valors. Pots fer-lo en una o en més d'una sentència. I ves amb compte perquè els temps han de ser numèrics 

Sandra	12'52

Isabel	12'25

Marta 	12'10

Maria 	12'07

Rosa 	11'95

Bea		11'97

Balma  	11'90

Anna  	12'74

1. Trau les participants de la carrera ordenades pel temps
1. Penalitza el temps de Bea amb 2 dècimes (0'2), i torna a traure les participants ordenades (Bea ha d'haver perdut 2 posicions, passant de tercera a cinquena posició)

![ref1]
## **Exercici 8.2 (MongoDB)**
Sobre la teua Base de Dades **MONGODB** treballarem sobre la col·lecció **libro**, la mateixa que hem utilitzat en els exemples. Si no la tens creada, executa les sentències del principi de la pregunta **3.4.2**. Fes les següents consultes. Copia-les en un únic fitxer de text, de forma numerada. És aquest fitxer el que hauràs de pujar.

1. Busca els llibres que tenen més de 500 pàgines. Visualitza el \_id, el títol i el número de pàgines
1. Busca els llibres de l'any 2014. Visualitza únicament títol i data
1. Busca els llibres de l'editorial Planeta. Visualitza únicament títol i editorial
1. Busca els llibres de l'editorial Planeta de més de 500 pàgines. Visualitza únicament títol, editorial i pàgines
1. Busca els llibres que no tenen editorial. Visualitza únicament títol i editorial
1. Busca els llibres que en el resum contenen la paraula **caballo**. Visualitza el resum per poder comprovar-ho. Han d'eixir 2 llibres, **Circo máximo** i **Las carreras de Escorpio**.
1. Utilitzant la funció **aggregate**, trau l'editorial i la mitjana de pàgines d'aquelles editorials que tenen una mitjana de pàgines superior a 500. Eixiran 3 editorials.

![ref1]
## **Exercici 8.3 (MongoDB)**
Aquest exercici l'has de realitzar sobre la teua BD de MongoDB.

title : Fight Club

writer : Chuck Palahniuk

year : 1999

actors : [

`  `Brad Pitt

`  `Edward Norton ]

title : Pulp Fiction

writer : Quentin Tarantino

year : 1994

actors : [

`  `John Travolta

`  `Uma Thurman ]

title : Inglorious Basterds

writer : Quentin Tarantino

year : 2009

actors : [

`  `Brad Pitt

`  `Diane Kruger

`  `Eli Roth ]

title : The Hobbit: An Unexpected Journey

writer : J.R.R. Tolkein

year : 2012

franchise : The Hobbit

title : The Hobbit: The Desolation of Smaug

writer : J.R.R. Tolkein

year : 2013

franchise : The Hobbit

title : The Hobbit: The Battle of the Five Armies

writer : J.R.R. Tolkein

year : 2012

franchise : The Hobbit

synopsis : Bilbo y compañía se ven obligados a participar en una guerra contra una serie de combatientes y evitar que la Lonely Mountain caiga en manos de una oscuridad creciente.

title : Pee Wee Herman's Big Adventure

title : Avatar

1. Inserir tots els documents anteriors. Ha de ser **obligatòriament** amb una única sentència, per a la qual cosa hauràs d'utilitzar variables, una per a cada document.
1. Consultar tots els documents
1. Obtenir els documents amb **writer** igual a **"Quentin Tarantino"**
1. Obtenir els documents amb **actors** que incloguen a **"Brad Pitt"**
1. Obtenir els documents amb **franchise** igual a **"The Hobbit"**
1. Obtenir totes les pel·lícules dels anys 90.
1. Obtenir les pel·lícules estrenades entre l'any 2000 i el 2010.
1. Agregar sinopsis a **"The Hobbit: An Unexpected Journey"**: 
   1. "Un hobbit reacio, Bilbo Baggins, se dirige a Lonely Mountain con un enérgico grupo de enanos para reclamar su hogar en la montaña, y el oro que contiene, del dragón Smaug".
1. Agregar sinopsis a **"The Hobbit: The Desolation of Smaug**": 
   1. "Los enanos, junto con Bilbo Baggins y Gandalf the Grey, continúan su búsqueda para recuperar Erebor, su tierra natal, de manos de Smaug. Bilbo Baggins está en posesión de un anillo misterioso y mágico".
1. Agregar un actor anomenat **"Samuel L. Jackson"** a la pel·lícula "Pulp Fiction"
1. Trobar les pel·lícules que en la sinopsis continguen la paraula **"Bilbo"**
1. Trobar les pel·lícules que en la sinopsis continguen la paraula **"Gandalf"**
1. Trobar les pel·lícules que en la sinopsis continguen la paraula **"Bilbo"** i no la paraula **"Gandalf"**. S'aconsella utilitzar l'operador **$and**
1. Trobar les pel·lícules que en la sinopsis continguen la paraula **"enanos"** o **"hobbit"**
1. Trobar les pel·lícules que en la sinopsis continguen les paraules **"oro"** i **"dragón"**
1. Eliminar la pel·lícula **"Pee Wee Herman's Big Adventure"**
1. Eliminar la pel·lícula **"Avatar"**

![ref1]
## **Exercici 8.4 (mongoDB)**
Sobre la teua Base de Dades MONGODB treballarem sobre la col·lecció **libro**, la mateixa que hem utilitzat en els exemples. Si no la tens creada, executa les sentències del principi de la pregunta **3.4.2**. Fes les següents consultes. Copia-les en un únic fitxer de text, de forma numerada. És aquest fitxer el que hauràs de pujar.

1. Incrementar el preu dels llibres de l'editorial Planeta en 2€ (recordeu que per a modificar més d'un document, hem de posar com a tercer paràmetre l'opció **{multi:true}** )
1. Crear el camp editorial amb el valor nul, per a tots aquells documents que no tinguen el camp editorial
1. Fer l'operació inversa: eliminar el camp editorial per a tots aquells que el tinguen nul
1. Traure l'any del llibre, a partir de la **fecha** (serà un camp calculat anomenat **año**)
1. Aprofita el camp anterior per a traure els llibres estrictament anteriors a l'any 2013. Visualitza **titulo**, **fecha** i **año**

![ref1]
## **Exercici 8.5 (eXist)**
Realitzar les expressions XPath que tornen les següents qüestions (totes elles sobre **Rutes.xml**):

1. Traure el nom de totes les rutes.
1. Traure el nom de les rutes amb un desnivell major que 600 m.
1. Traure les rutes en les quals el desnivell acumulat duplica el desnivell. (**Observació**: quan en una condició combinem alguna operació amb una comparació, és millor posar l'operació abans de l'operador de comparació)
1. Traure el nom del primer punt de cada ruta.
1. Traure el nom de l'últim punt de cada ruta
1. Traure els punts de la tercera ruta.
1. Traure el número de punts de la tercera ruta
1. Traure el nom de les rutes que tenen estrictament més de 5 punts.
1. Traure la mitjana de desnivell de les rutes
1. Traure les rutes en les quals hi ha alun punt més avall del paral·lel 40

![ref1]
## **Exercici 8.6 (eXist)**
Fer les expressions XQuery per a aconsequir:

1\. El mòdul amb el nom del professor com a atribut:

<modul professor="Joan Puig">Llenguatges de Marques</modul>

2\. El nom de cada ruta amb el número de punts com a argument:

<rutes>

<ruta numPunts="5">Pujada a Penyagolosa</ruta>

<ruta numPunts="7">La Magdalena</ruta>

<ruta numPunts="6">Pelegrins de Les Useres</ruta>

<ruta numPunts="6">Catí - Sant Pere de Castellfort</ruta>

</rutes>

` `3. Cada ruta amb el nom com a atribut, la latitud mitjana dels seus punts i la longitud mitjana

<ruta nom="Pujada a Penyagolosa">

<lat\_mitj>40.2408508</lat\_mitj>

<long\_mitj>-0.3515282</long\_mitj>

</ruta>

<ruta nom="La Magdalena">

<lat\_mitj>40.01264257142857</lat\_mitj>

<long\_mitj>-0.02034042857142857</long\_mitj>

</ruta>

...

` `4. La mitjana de punts de les rutes

6

**This document was truncated here because it was created in the Evaluation Mode.**
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis.002.png
