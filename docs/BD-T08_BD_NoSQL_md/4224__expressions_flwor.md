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

[« Anterior](4223__expressions_avaluables.md) | [Següent »](4225__alternatives.md)
# **4.2.2.4 - Expressions FLWOR**
Les expressions FLWOR són la part més potent d’XQuery. Estan formades per cinc instruccions opcionals que permeten fer les consultes i alhora processar-les per seleccionar els ítems que interessen d’una seqüència.

|**           |**Clàusula**|**Ús**|
| :-: | :-: | :-: |
|**f**|**for**|Permet recórrer una seqüència, agafant cada vegada un element d'aquesta|
|**l**|**let**|Serveix per assignar valors a una variable|
|**w**|**where**|Permet filtrar els resultats segons condicions|
|**o**|**order by**|Ordena els resultats abans de mostrar-los|
|**r**|**return**|Retorna el resultat de tota l’expressió|

"FOR ... RETURN"

La instrucció **for** es fa servir per avaluar individualment cadascun dels resultats d’una seqüència de nodes. En un **for** es defineixen dues coses:

- Una variable, que serà la que anirà agafant els elements de la seqüència un per un.
- La paraula clau **in**, en la qual es defineix quina és la seqüència d’elements per processar.

La manera més senzilla d’expressió FLWOR és combinar el **for** amb el **return** per retornar els valors obtinguts de manera seqüencial: 

for $i in ('Hola' , 'Adéu' )

return $i

generarà:

Hola

Adéu

Les seqüències de valors poden ser de qualsevol tipus. Per exemple, poden ser números. Així, el següent exemple:

for $i in (1,2,3)

return $i \* $i

generarà:

1

4

9

O bé una seqüència de nodes, per mig d'una expressió XPath. Per exemple amb l’expressió següent capturem una seqüència de nodes i els fem servir per obtenir-ne el cognom:

for $alumne in //alumne

return <alumne> { $alumne/cognoms } </alumne>

generarà:

<alumne>
`   `<cognoms>Alegre</cognoms>
</alumne>
<alumne>
`   `<cognoms>Balaguer</cognoms>
</alumne>
<alumne>
`   `<cognoms>Centelles</cognoms>
</alumne>

Es pot veure que els valors del **return** s’han anat processant un per un i per aquest motiu es repeteixen les etiquetes **<alumne>**.

Un aspecte important és que no cal que el **for** siga la primera expressió de la consulta. També es pot posar com a paràmetre en una funció XPath.

Per exemple, l’expressió següent ens tornarà el nombre d’alumnes: 

count (

for $alumne in //alumne

return $alumne

)

3

En el **for** es pot incloure l’operador **at**, que permet obtenir la posició del node que s’està processant. Amb aquest operador podem fer que aparega el número d’ordre en els resultats.

for $alumne at $pos in //alumne 

return <alumne numero="{$pos}">

{ $alumne/cognoms/text() }

</alumne>

que donarà

<alumne numero="1">Alegre</alumne>
<alumne numero="2">Balaguer</alumne>
<alumne numero="3">Centelles</alumne>



"FOR NIUAT" ("anidat")

Les ordres **for** es poden posar unes dins d'unes altres, d’una manera similar a com ho fa SQL amb les subconsultes. Així es poden aconseguir resultats més complexos que es basen en els resultats obtinguts anteriorment.

for $selec in //alumne 

return 

`    `<persona> 

`        `{ $selec/nom } 

`        `{ 

`            `for $selec2 in $selec 

`            `return $selec2//cognom 

`        `} 

`    `</persona>

<persona>
`    `<nom>Albert</nom>
</persona>
<persona>
`    `<nom>Bernat</nom>
</persona>
<persona>
`    `<nom>Joan</nom>
</persona> 

Aquesta sentència anterior queda un poc pobra, ja que en el document hi ha molt poques dades.

Un exemple un poc més complet (i comprensiu) seria el següent:

for $selec in //ruta 
return 
`    `<ruta> 
`        `<nomRuta>
`        `{ $selec/nom/text() }
`        `</nomRuta>
`        `<punts>
`        `{ 
`            `for $selec2 in $selec//punt 
`            `return <punt> {$selec2/nom/text()} </punt> 
`        `}
`        `</punts>
`    `</ruta>

que donaria el sagüent resultat:

<ruta> 

<nomRuta>Pujada a Penyagolosa</nomRuta>

<punts> 

<punt>Sant Joan</punt>

<punt>Encreuament</punt>

<punt>Barranc de la Pegunta</punt>

<punt>El Corralico</punt>

<punt>Penyagolosa</punt>

</punts>

</ruta>

<ruta> 

<nomRuta>La Magdalena</nomRuta>

<punts> 

<punt>Primer Molí</punt>

<punt>Segon Molí</punt>

<punt>Caminàs</punt>

<punt>Riu Sec</punt>

<punt>Sant Roc</punt>

<punt>Explanada</punt>

<punt>La Magdalena</punt>

</punts>

</ruta>


...



LET

Ens permet declarar variables i assignar-los un valor. Sobretot es fa servir per guardar valors que s’han de fer servir més tard.

let $num := 1

let $nom := "Pere"

let $i := (1 to 3)

En les expressions FLWOR hi pot haver tants **let** com calga.

for $alumne in doc("db/Tema9/classe.xml")//alumne

let $nom := $alumne/nom

let $nota := $alumne/nota

return <nom>{ concat($nom,": ",$nota) }</nom>

<nom>Albert: 6</nom>
<nom>Bernat: 3</nom>
<nom>Joan: 8</nom>

S’ha d’anar amb compte amb **let** perquè el seu funcionament és molt diferent del de **for**:

- **for** s’executa per a cada membre d’una seqüència.
- **let** fa referència al seu valor en conjunt. Si és una seqüència, el que es processa són tots els valors de cop.

Podem veure la diferència amb un exemple. Aquesta instrucció amb **for**:

for $selec in //alumne

return <persona>{$selec/nom}</persona>

Dóna:

persona>
`    `<nom>Albert</nom>
</persona>
<persona>
`    `<nom>Bernat</nom>
</persona>
<persona>
`    `<nom>Joan</nom>
</persona>

I en canvi amb **let**:

let $selec := //alumne

return <persona>{$selec/nom}</persona>

Donarà:

<persona>
`    `<nom>Albert</nom>
`    `<nom>Bernat</nom>
`    `<nom>Joan</nom>
</persona>

Els resultats són bastant diferents! Es pot veure clarament que **let** ha tractat tots els valors de cop.



WHERE

La instrucció **where** és la part que indicarà quin filtre s’ha de posar a les dades rebudes abans d’enviar-les a la sortida del **return**. Normalment en el filtre es fa servir algun tipus de predicat XPath:

for $alumne in //alumne

where $alumne/@aprovat="si"

return $alumne/nom

<nom>Albert</nom>
<nom>Joan</nom>

Com que XPath forma part d’XQuery moltes vegades el mateix filtre es pot definir de diverses maneres. Per exemple, aquesta expressió és equivalent a l’anterior:

for $alumne in //alumne[@aprovat="si"]

return $alumne/nom

Això sí, en un **where** hi pot haver tantes condicions com faça falta simplement encadenant-les amb les operacions lògiques **and**, **or** o **not()**.

Aquesta expressió retorna el cognom dels alumnes que han aprovat i que es diuen *Joan*:

for $alumne in //alumne
where $alumne/@aprovat="si" and $alumne/nom="Joan"
return $alumne/cognoms

<cognoms>Centelles</cognoms>

El **where** afegeix més potència del que sembla, ja que ens permet fer els **inner joins** d’SQL en fitxers XML. Per exemple, a partir de dos fitxers amb les dades de dues classes diferents es poden obtenir només els alumnes que es repeteixen entre les dues classes amb:

for $alum1 in doc("db/Tema9/classe.xml")//alumne

let $alum2 in doc("db/Tema9/classe2.xml")//alumne

where $alum1 = $alum2

**This document was truncated here because it was created in the Evaluation Mode.**
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
