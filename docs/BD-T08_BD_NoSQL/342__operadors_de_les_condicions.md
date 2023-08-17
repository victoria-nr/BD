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

[« Anterior](341__parmetres_de_les_funcions_find_i_findone.md) | [Següent »](343__agregaci.md)
# **3.4.2 - Operadors de les condicions**
Abans de començar aquesta pregunta, anem a agafar unes dades de prova, que estan en el fitxer **libros\_ejemplo.json**

Només heu de copiar el contingut del fitxer en la terminal del client de Mongo.

Posem ací el contingut per a que pugueu pegar-li una miradeta sense necessitat d'obrir-lo. Anirà bé per als exemples posteriors.

db.libro.save({
`    `"\_id":"9788408117117",
`      `"titulo":"Circo Máximo",
`    `"autor":"Santiago Posteguillo",
`    `"editorial":"Planeta",
`    `"enstock":true,
`    `"paginas":1100,
`    `"precio":21.75,
`    `"fecha":new ISODate("2013-08-29T00:00:00Z"),        
`      `"resumen":"Circo Máximo, de Santiago Posteguillo, que ha escrito otras obras de narrativa histórica como Las Legiones Malditas o La traición de Roma, es la segunda parte de la trilogía de Trajano, que comenzó con Los asesinos del emperador, un relato impactante, descomunal, descrito con un trepidante pulso narrativo destinado a trasla dar al lector a la Roma imperial de los césares. Santiago posteguillo se ha convertido en el autor español de referencia de la novela histórica sobre Roma y el mundo antiguo. Bienvenidos al mundo de Marco Ulpio Trajano. Circo Máximo es la historia de Trajano y su gobierno, guerras y traiciones, lealtades insobornables e historias de amor imposibles. Hay una vestal, un juicio, inocentes acusados, un abogado especial, mensajes cifrados, códigos secretos, batallas campales, fortalezas inexpugnables, asedios sin fin, dos aurigas rivales, el Anfiteatro, los gladiadores y tres carreras de cuadrigas. Hay también un caballo especial, diferente a todos, leyes antiguas olvidadas, sacrificios humanos, amargura y terror, pero también destellos de nobleza y esperanza, como la llama de Vesta, que mientras arde preserva a Roma. Sólo que hay noches en las que la llama del Templo de Vesta tiembla. La rueda de la Fortuna comienza entonces a girar. En esos momentos, todo puede pasar y hasta la vida del propio Trajano, aunque él no lo sepa, corre peligro. Y, esto es lo mejor de todo, ocurrió: hubo un complot para asesinar a Marco Ulpio Trajano."
})

db.libro.save({
`     `"\_id":"9788401342158",
`      `"titulo":"El juego de Ripper",
`      `"autor":"Isabel Allende",
`      `"editorial":"Plaza & Janes",
`      `"enstock":true,
`      `"paginas":480,
`      `"precio":21.75,
`    `"fecha":new ISODate("2014-03-01T00:00:00Z"),        
`      `"resumen":"Tal como predijo la astróloga más reputada de San Francisco, una oleada de crímenes comienza a sacudir la ciudad. En la investigación sobre los asesinatos, el inspector Bob Martín recibirá la ayuda inesperada de un grupo de internautas especializados en juegos de rol, Ripper. 'Mi madre todavía está viva, pero la matará el Viernes Santo a medianoche', le advirtió Amanda Martín al inspector jefe y éste no lo puso en duda, porque la chica había dado pruebas de saber más que él y todos sus colegas del Departamento de Homicidios. La mujer estaba cautiva en algún punto de los dieciocho mil kilómetros cuadrados de la bahía de San Francisco, tenían pocas horas para encontrarla con vida y él no sabía por dónde empezar a buscarla",
` `})

db.libro.save({
`    `"\_id":"9788496208919",
`   `"titulo":"Juego de tronos: Canción de hielo y fuego 1",
`   `"autor":"George R.R. Martin",
`   `"editorial":"Gigamesh",
`   `"enstock":true,
`   `"paginas":793,
`   `"precio":9.5,
`   `"fecha":new ISODate("2011-11-24T00:00:00Z"),     
`   `"resumen":"Tras el largo verano, el invierno se acerca a los Siete Reinos. Lord Eddars Stark, señor de Invernalia, deja sus dominios para unirse a la corte del rey Robert Baratheon el Usurpador, hombre díscolo y otrora guerrero audaz cuyas mayores aficiones son comer, beber y engendrar bastardos. Eddard Stark desempeñará el cargo de M ano del Rey e intentará desentrañar una maraña de intrigas que pondrá en peligro su vida... y la de los suyos. En un mundo cuyas estaciones duran décadas y en el que retazos de una magia inmemorial y olvidada surgen en los rincones más sombrios y maravillosos, la traición y la lealtad, la compasión y la sed de venganza, el amor y el poder hacen del juego de tronos una poderosa trampa que atrapa en sus fauces a los personajes... y al lector. 'El regreso triunfal de Martin a la fantasía de más alta calidad... con personajes desarrollados con maestría, prosa hábil y pura obstinación.'"
})

db.libro.save({
`  `"\_id":"9788499088075",
`  `"titulo":"La ladrona de libros",
`  `"autor":"Markus Zusak",
`  `"editorial":"Debolsillo",
`  `"enstock":false,
`  `"paginas":544,
`  `"precio":9.45,
`  `"fecha":new ISODate("2009-01-09T00:00:00Z"),      
`  `"resumen":"En plena II Guerra Mundial, la pequeña Liesel hallará su salvación en la lectura. Una novela preciosa, tremendamente humana y emocionante, que describe las peripecias de una niña alemana de nueve años desde que es dada en adopción por su madre hasta el final de la guerra. Su nueva familia, gente sencilla y nada afecta al na zismo, le enseña a leer y a través de los libros Rudy logra distraerse durante los bombardeos y combatir la tristeza. Pero es el libro que ella misma está escribiendo el que finalmente le salvará la vida.",
})

db.libro.save({
`  `"\_id":"9788415140054",
`  `"titulo":"La princesa de hielo",
`  `"autor":"Camilla Lackberg",
`  `"editorial":"Embolsillo",
`  `"enstock":true,
`  `"precio":11,
`  `"fecha":new ISODate("2012-10-30T00:00:00Z"),    
`  `"resumen":"Misterio y secretos familiares en una emocionante novela de suspense Erica vuelve a su pueblo natal tras el fallecimiento de sus padres, pero se va a encontrar con un nuevo drama. Aparentemente su amiga de la infancia, Alex, se ha suicidado. Pronto se descubre que no solamente fue asesinada sino que estaba embarazada. El primer sospechoso es Anders, un artista fracasado con quien Alex mantenía una relación especial. Pero poco después de ser liberado por falta de pruebas, Anders aparece muerto en su domicilio. Con la ayuda del comisario Patrik, Erica investigará el pasado de su amiga Alex."
})

db.libro.save({
`  `"\_id":"9788408113331",
`  `"titulo":"Las carreras de Escorpio",
`  `"autor":"Maggie Stiefvater",
`  `"editorial":"Planeta",
`  `"enstock":false,
`  `"paginas":290,
`  `"precio":17.23,
`  `"fecha":new ISODate("2013-06-04T00:00:00Z"),  
`  `"resumen":"En la pequeña isla de Thisby, cada noviembre los caballos de agua de la mitología celta emergen del mar. Y cada noviembre, los hombres los capturan para participar en una emocionante carrera mortal. En las carreras de Escorpio, algunos compiten para ganar. Otros para sobrevivir. Los jinetes intentan dominar a sus caballos de agua el tiempo suficiente para acabar la carrera. Algunos lo consiguen. El resto, muere en el intento. Sean Kendrick es el favorito, y necesita ganar la carrera para ganar, también, su libertad. Pero Puck Connolly está dispuesta a ser su más dura adversaria. Ella nunca quiso participar en las carreras. Pero no tiene elección: o compite y gana o… lo pierde todo.",
})

db.libro.save({
`  `"\_id":"9788468738895",
`  `"titulo":"Las reglas del juego",
`  `"autor":"Anna Casanovas",
`  `"enstock":true,
`  `"paginas":null,
`  `"precio":15.90,
`  `"fecha":new ISODate("2014-02-06T00:00:00Z"),
`  `"resumen":"Susana Lobato tiene la vida perfectamente planeada y está a punto de conseguir todo lo que quiere: va a tener su propio programa de noticias económicas y en dos meses va a casarse con un hombre maravilloso. Pero una noche Tim anula la boda y la abandona para perseguir un sueño que no la incluye a ella.Kev MacMurray acaba de cumplir treinta y cinco años y siente que ha llegado el momento de dar un cambio a su vida. No sabe por qué, pero últimamente se está asfixiando y está convencido de que no puede seguir donde está. Lo único que lo retiene es la boda de Tim, su mejor amigo.Pero Tim anula la boda y una noche Kev coincide con Susana y respira por primera vez en mucho tiempo.¿Por qué no le había sucedido antes? Se suponía que él y Susana no se soportaban ¿Desde cuándo siente que si no besa a la prometida de su mejor amigo no podrá seguir respirando?Susana nunca había reaccionado así con nadie. ¿Puede correr el riesgo de averiguar qué pasará si se entrega a Kev?Y qué pasará si vuelve Tim, ¿podrán dar un paso atrás?.",
})

Com podeu comprovar estan els comandos d'inserció (**save()** ) i també es veu prou bé els camps de cada document.

Podeu veure que hi ha 7 documents en la nova col·lecció **libro**:

\> db.libro.count()
7

I també podem consultar els títols de forma còmoda:

\> db.libro.find( {} , {titulo:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo" }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper" }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1" }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros" }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo" }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

I un altre exemple, on consultem els llibres que estan en stock (hi ha un camp booleà que ho diu: **enstock**), mostrant títol, editorial i preu

\> db.libro.find( {enstock: true} , {titulo:1 , editorial:1 , precio:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "editorial" : "Planeta", "precio" : 21.75 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "editorial" : "Plaza & Janes", "precio" : 21.75 }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "editorial" : "Gigamesh", "precio" : 9.5 }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "editorial" : "Embolsillo", "precio" : 11 }

I un últim exemple, on consultem els llibres que estan en stock i tenen un preu de 21.75 €, mostrant tot excepte el \_id i el resum

\> db.libro.find( {enstock: true , precio: 21.75} , {titulo:1 , editorial:1 , precio:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "editorial" : "Planeta", "precio" : 21.75 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "editorial" : "Plaza & Janes", "precio" : 21.75 }

Anem a mirar ara operadors que ens serviran per fer millor les consultes.

Operadors de comparació

Fins ara en totes les condicions hem utilitzat la igualtat, si un determinat camp era igual a un determinat valor. Però hi ha infinitat de consultes en les quals voldrem altres operacions de comparació: major, major o igual, menor, ...

Aquestos són els operadors de comparació:

- **$lt** (*less than*) **menor**
- **$lte** (*less than or equal*) **menor o igual**
- **$gt** (*gretaer than*) major
- **$gte** (*gretaer than or equal*) **major o igual**
- **$ne** (*not equal*) **distint**
- **$eq** (*equal*) **igual** (però aquest quasi que no caldria, perquè en no posar res es refereix a la igualtat com fins ara)

La sintaxi per a la seua utilització és, com sempre, acoplar-se a la sintaxi JSON:

clau : { $operador : valor [, ... ] }

Així per exemple, per a buscar els llibres de més de 10 €:

\> db.libro.find( { precio : { $gt : 10 } } , { titulo:1 , precio:1 } )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "precio" : 21.75 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "precio" : 21.75 }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "precio" : 11 }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "precio" : 17.23 }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "precio" : 15.9 }

I per a buscar els llibres entre 10 i 20 €:

\> db.libro.find( { precio : { $gt : 10 , $lt:20 } } , { titulo:1 , precio:1 } )
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "precio" : 11 }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "precio" : 17.23 }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "precio" : 15.9 }

És especialment útil per a les dates, ja que difícilment trobarem una data (i hora) exacta, i voldrem quasi sempre els documents anteriors a una data, o posteriors, o entre dues dates. Haurem d'anar amb compte pel tractament especial de les dates: hem de comparar coses del mateix tipus, i per tant la data amb la qual volem comparar l'haurem de tenir en forma de data:

\> var d = new ISODate("2013-01-01T00:00:00Z")
\> db.libro.find( {fecha:{$gte:d} } , {fecha:1} )
{ "\_id" : "9788408117117", "fecha" : ISODate("2013-08-29T00:00:00Z") }
{ "\_id" : "9788401342158", "fecha" : ISODate("2014-03-01T00:00:00Z") }
{ "\_id" : "9788408113331", "fecha" : ISODate("2013-06-04T00:00:00Z") }
{ "\_id" : "9788468738895", "fecha" : ISODate("2014-02-06T00:00:00Z") }

$in

Servirà per a comprovar si el valor d'un camp està entre els d'una llista, proporcionada com un array. La sitaxi és:

clau : { $in : [valor1 , valor2 , ... , valorN] }

I ací tenim un exemple, els llibre de les editorials Planeta i Debolsillo:

\> db.libro.find( { editorial: {$in : ["Planeta" , "Debolsillo"]} } , {titulo:1 , editorial:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "editorial" : "Planeta" }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "editorial" : "Debolsillo" }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "editorial" : "Planeta" }

$nin

És el contrari, traura els que no estan en la llista.

\> db.libro.find( { editorial: {$nin : ["Planeta" , "Debolsillo"]} } , {titulo:1 , editorial:1} )
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "editorial" : "Plaza & Janes" }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "editorial" : "Gigamesh" }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "editorial" : "Embolsillo" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

Observeu com també trau els llibres que no tenen editorial, com és el cas de l'últim llibre, Las reglas del juego

$or

L'operador anterior, **$in**, ja feia una espècie de OR, però sempre sobre el mateix camp. Si l'operació OR la volem fer sobre camps distints, haurem d'utilitzar l'operador **$or**. La seua sintaxi ha de jugar amb la possibilitat de posar molts elements, i per tant convé l'array:

$or : [ {clau1:valor1} , {clau2:valor2} , ... , {clauN:valorN} ]

Serà cert si s'acompleix alguna de les condicions. Per exemple, traure els llibres que no estan en stock o que no tenen editorial:

\> db.libro.find( { $or : [ {enstock:false} , {editorial:null} ] } , {titulo:1 , enstock:1 , editorial:1} )
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "editorial" : "Debolsillo", "enstock" : false }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "editorial" : "Planeta", "enstock" : false }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "enstock" : true }

$not

Serveix per a negar una altra condició.

$not : { condició }

Per exemple els llibres que no són de l'editorial Planeta (observeu que seria més senzill utilitzar l'operador **$ne**, però és per a mostrar el seu funcionament:

\> db.libro.find( { editorial: {$not : {$eq:"Planeta"} } } , {titulo:1 , editorial:1} )
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "editorial" : "Plaza & Janes" }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "editorial" : "Gigamesh" }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "editorial" : "Debolsillo" }
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo", "editorial" : "Embolsillo" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

$exists

Servirà per a saber els documents que tenen un determinat camp

clau : { $exists : *boolean* }

Depenet del valor *boolean*, el funcionament serà:

- **true**: torna els documents en els quals existeix el camp, encara que el seu valor siga nul
- **false**: torna els documents que no tenen el camp.

Anem a traure els llibres que tenen el camp **paginas**:

\> db.libro.find( { paginas: {$exists:true} } , {titulo:1 , paginas:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "paginas" : 1100 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "paginas" : 480 }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "paginas" : 793 }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "paginas" : 544 }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "paginas" : 290 }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "paginas" : null }

Observeu com ens apareix també l'ultim llibre, que té el camp **paginas** amb el valor **nul**. En canvi si haguérem fet la consulta preguntant pels que són diferent de nul, no apareixeria aquest últim llibre:

\> db.libro.find( { paginas: {$ne:null} } , {titulo:1 , paginas:1} )
{ "\_id" : "9788408117117", "titulo" : "Circo Máximo", "paginas" : 1100 }
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper", "paginas" : 480 }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1", "paginas" : 793 }
{ "\_id" : "9788499088075", "titulo" : "La ladrona de libros", "paginas" : 544 }
{ "\_id" : "9788408113331", "titulo" : "Las carreras de Escorpio", "paginas" : 290 }

I si posem **false** al valor en el **$exists**, únicament ens apareixerà el llibre que no té el camp:

\> db.libro.find( { paginas: {$exists:false} } , {titulo:1 , paginas:1} )
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo" }

I per la mateixa raó que abans, si traiem els que tenen paginas a null, ens eixirà tant qui no té el camp, com qui el té però amb valor nul:

\> db.libro.find( { paginas: null } , {titulo:1 , paginas:1} )
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego", "paginas" : null }

Per tant, per a segons quines coses, ens interessa l'operador **$exists**, en compte de jugar amb el nul.

Expressions regulars

Mongo accepta les expressions regulars de forma nativa, cosa que dóna molta potència per a poder buscar informació diversa.

Les expressions regulars en Mongo tenen la mateixa sintaxi que en Perl, i que és molt molt pareguda a la major part de llenguatges de programació.

Mirem alguns exemples. Els llibres dins dels quals està la paraula **juego**:

\> db.libro.find( { titulo: /juego/ } , {titulo:1} )
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

Ara que tenen la paraula **juego** sense importar majúscules o minúscules:

\> db.libro.find( { titulo: /juego/i } , {titulo:1} )
{ "\_id" : "9788401342158", "titulo" : "El juego de Ripper" }
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

I ara que tenen la paraula **juego** només al principi.

\> db.libro.find( { titulo: /^juego/i } , {titulo:1} )
{ "\_id" : "9788496208919", "titulo" : "Juego de tronos: Canción de hielo y fuego 1" }

I ara els llibres que en el reusum (**resumen**) que tenen la paraula **amiga** o **amigo**, és a dir **amig** seguit d'una **a** o una **o**:

\> db.libro.find( { resumen: /amig[ao]/i } , {titulo:1} )
{ "\_id" : "9788415140054", "titulo" : "La princesa de hielo" }
{ "\_id" : "9788468738895", "titulo" : "Las reglas del juego" }

Arrays

Les consultes dins d'arrays de Mongo són molt senzilles.

La més senzilla és com quan busquem un valor d'un tipus senzill, i en aquest cas el que farà Mongo és buscar en tot l'array per si està aquest valor. És a dir, exactament igual que el que hem fet fins ara.

db.col\_leccio1.find ( { clau\_array : valor } )

Mirem-ho en un exemple. Anem a crear dos documents que tinguen un array cadascun, per exemple de colors. El creem en una col·lecció nova, anomenada **colorins**, en dos documents amb el mateix camp de tipus array, **color**, però amb dades diferents:

\> db.colorins.insert({color: ["roig","blau","groc"]})
WriteResult({ "nInserted" : 1 })

\> db.colorins.insert({color: ["negre","blanc","roig"]})
WriteResult({ "nInserted" : 1 })

\> db.colorins.find();
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }


Com es veu en la sintaxi, triar els documents que tenen un camp (en aquest cas d'array) que continga un valor, és igual de senzill que quan es tracta d'un camp de tipus string, per exemple:

\> db.colorins.find({color:"roig"})
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }

També podem utilitzar qualsevol dels operadors vistos fins el moment, com per exemple l'operador **$in**, que mirarà els documents que tenen algun dels colors que s'especifica a continuació:

\> db.colorins.find({color: {$in : ["groc","lila"]} })
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }

O per exemple també utilitzar **expressions regulars**:

\> db.colorins.find({color: /bl/ })
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }

**$all**

L'operador **$all** el podem utilitzar quan vulguem seleccionar els documents que en l'array tiguen **tots** els elements especificats.

Per exemple, anem a buscar els document que tenen el color roig i blau.

\> db.colorins.find({color : { $all : ["roig","blau"]} })
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }

**Subíndex**

Si volem mirar exactament una determinada posició de l'array, podem especificar la posició immediatament després de la clau, **separada per un punt**. Recordeu que la primera posició és la **0**. Hem de posar entre cometes la clau i la posició, sinó no sabrà trobar-la.

Per exemple, busquem els documents que tenen el roig en la primera posició.

\> db.colorins.find({"color.0" : "roig"} )
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }

**Nota**

Accedir a una determinada posició és fàcil, però no és tan fàcil accedir a una posició calculada, per exemple a l'última posició. Ja fa falta coneixements un poc més avançats de JavaScript, per a posar dins del **find()** una funció en JavaScript, i actuar dins d'aquesta.

Únicament de manera il·lustrativa, posem ací la manera de traure els documents, l'últim color dels quals és el roig. En ella ens creem una variable amb l'últim element de l'array (amb **pop()**), i el comparem amb el color roig, tornant true en cas de que sí que siguen iguals:

\> db.colorins.find(function() { var a =this.color.pop(); return (a =="roig")}  )
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }

També hi ha una forma alternativa de fer-ho, que és utilitzant l'operador $where, que ens permet crear condicions amb sintaxi JavaScript:

\> db.colorins.find({$where:"this.color[this.color.length - 1]=='roig'"})
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }

**$size**

L'operador **$size** ens servirà per a fer condicions sobre el número d'elements d'un array.

Incorporem 2 documents nous, amb 2 i 4 elements respectivament, per a poder comprovar-lo:

\> db.colorins.insert({color: ["negre","blanc"]})
WriteResult({ "nInserted" : 1 })

\> db.colorins.insert({color: ["taronja","gris","lila","verd"]})
WriteResult({ "nInserted" : 1 })

\> db.colorins.find()
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }
{ "\_id" : ObjectId("56e16972aa3c92aaed389da6"), "color" : [ "negre", "blanc" ] }
{ "\_id" : ObjectId("56e16990aa3c92aaed389da7"), "color" : [ "taronja", "gris", "lila", "verd" ] }

Ara anem a seleccionar els documents que tenen 4 colors

\> db.colorins.find({color:{$size:4}})
{ "\_id" : ObjectId("56e16990aa3c92aaed389da7"), "color" : [ "taronja", "gris", "lila", "verd" ] }

**Nota**

L'operador **$size** només admet un valor numèric, i no es poden concatenar expressions amb altres operadors, com per exemple intentar la condició que la grandària de l'array siga menor o igual a un determinat valor. Es pot tornar a esquivar la qüestió amb l'operador **$where**, i posar la condició en JavaScript. Així la consulta dels documents que tenen 3 o menys colors la podríem traure d'aquesta manera:

\> db.colorins.find({$where:"this.color.length<=3"})
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau", "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc", "roig" ] }
{ "\_id" : ObjectId("56e16972aa3c92aaed389da6"), "color" : [ "negre", "blanc" ] }

**$slice**

L'operador **$slice** no és un operador que es puga posar en les condicions (criteris), sinó que servirà per a extraure determinats elements de l'array, pel número d'ordre d'aquestos elements en e l'array. Només el podrem posar, per tant, en el segon paràmetre del **find()**.

La sintaxi és:

clau : {$slice : x }

Els valors que pot agafar **x** són:

- Números positius: serà el número d'elements del principi (per l'esquerra)
- Números negatius: serà el número d'elements del final (per la dreta)
- Un array de 2 elements (**[x,y]**): traurà a partir de la posició **x** (0 és el primer), tants elements com indique **y**

Per exemple, anem a traure els dos primers colors de cada document:

\> db.colorins.find({} , {color:{$slice:2} })
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "roig", "blau" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "negre", "blanc" ] }
{ "\_id" : ObjectId("56e16972aa3c92aaed389da6"), "color" : [ "negre", "blanc" ] }
{ "\_id" : ObjectId("56e16990aa3c92aaed389da7"), "color" : [ "taronja", "gris" ] }

O traure l'últim color:

\> db.colorins.find({} , {color:{$slice:-1 }})
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "roig" ] }
{ "\_id" : ObjectId("56e16972aa3c92aaed389da6"), "color" : [ "blanc" ] }
{ "\_id" : ObjectId("56e16990aa3c92aaed389da7"), "color" : [ "verd" ] }

O traure el tercer element, tinguen els que tinguen. Recordeu que el segon element, és el de la posició 2, i en volem traure 1.

\> db.colorins.find({} , {color:{$slice:[2,1] }})
{ "\_id" : ObjectId("56e1438ff6663c8169030e09"), "color" : [ "groc" ] }
{ "\_id" : ObjectId("56e14398f6663c8169030e0a"), "color" : [ "roig" ] }
{ "\_id" : ObjectId("56e16972aa3c92aaed389da6"), "color" : [ ] }
{ "\_id" : ObjectId("56e16990aa3c92aaed389da7"), "color" : [ "lila" ] }

Recerques en objectes

Per a fer recerques en camps que a la seua vegada són objectes (o documents dins de documents, en la terminologia de Mongo), només hem de posar la ruta de les claus separant per mig de punts, i cuider de posar-les entre cometes.

Així, per exemple, anem a fer una consulta sobre la col·lecció d'alumnes, que eren uns documents en els quals hi havia algun camp de tipus objecte.

\> db.alumnes.find().pretty()
{
`    `"\_id" : ObjectId("56debe3017bf4ed437dc77c8"),
`    `"nom" : "Abel",
`    `"cognoms" : "Bernat Cantera",
`    `"edat" : 22,
`    `"adreça" : {
`        `"carrer" : "Major",
`        `"numero" : 7,
`        `"cp" : "12502"
`    `},
`    `"nota" : [
`        `9.5,
`        `9
`    `]
}
{
`    `"\_id" : ObjectId("56dfdbd136d8b095cb6bd57a"),
`    `"nom" : "Berta",
`    `"cognoms" : "Bernat Cantero"
}

Es podrien traure els documents (els alumnes) que viuen en el codi postal 12502. Ens ha d'eixir l'únic alumne del qual tenim l'adreça, que justament té aquest codi postal. Recordeu que en la clau (realment clau.subclau), ha d'anar entre cometes. Hem posat al final **pretty()** per a una millor lectura, però evidentment no és necessari.

\> db.alumnes.find({"adreça.cp": "12502"}).pretty()
{
`    `"\_id" : ObjectId("56debe3017bf4ed437dc77c8"),
`    `"nom" : "Abel",
`    `"cognoms" : "Bernat Cantera",
`    `"edat" : 22,
`    `"adreça" : {
`        `"carrer" : "Major",
`        `"numero" : 7,
`        `"cp" : "12502"
`    `},
`    `"nota" : [
`        `9.5,
`        `9
`    `]
}

I funcionaria igual amb qualsevol número de subnivells, és a dir, documents que tenen objectes, els quals tenen objectes, ... I també amb altres tipus d'operadors, o expressions regulars, ...

Per exemple, tots els alumnes de Castelló (el codi postal ha de començar per 12 i contenir 3 xifres més, és a dir, caràcter del 0 al 9, i 3 vegades.

\> db.alumnes.find({"adreça.cp": /^12[0-9]{3}/}).pretty()
{
`    `"\_id" : ObjectId("56debe3017bf4ed437dc77c8"),
`    `"nom" : "Abel",
`    `"cognoms" : "Bernat Cantera",
`    `"edat" : 22,
`    `"adreça" : {
`        `"carrer" : "Major",
`        `"numero" : 7,
`        `"cp" : "12502"
`    `},
`    `"nota" : [
`        `9.5,
`        `9
`    `]
}

Limit, Skip i Sort

Una vegada tenim feta una consulta, podem limitar el nombre de documents que ens ha de tornar, o ordenar-los.

**This document was truncated here because it was created in the Evaluation Mode.**
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
