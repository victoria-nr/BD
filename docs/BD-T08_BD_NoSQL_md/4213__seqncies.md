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

[« Anterior](4212__navegaci.md) | [Següent »](4214__funcions.md)
# <a name="main"></a>**4.2.1.3 - Seqüències**
Una seqüència és una expressió XPath que retorna més d’un element. S’assemblen prou a les llistes d’altres llenguatges:

- Tenen ordre
- Permeten duplicats
- Poden contenir valors de tipus diferent en cada terme

És fàcil crear seqüències, ja que només cal tancar-les entre parèntesis i separar cadascun dels termes amb comes. L’expressió següent aplicada a qualsevol document: 

(1,2,3,4)

Retorna la seqüència de nombres d’un en un:

1

2

3

4

També es poden crear seqüències a partir d’expressions XPath. En aquest cas s’avaluarà primer la primera expressió, després la segona, etc. 

(//alumnes//nom/text() , //cognoms/text())

` `Aplicat al nostre exemple retornarà primer tots els noms dels alumnes i després tots els cognoms (de professor i alumnes): 

Albert

Bernat

Joan

Puig

Alegre

Balaguer

Centelles



Unió, Intersecció i disjunció

També es pot operar amb les seqüències d’elements amb els operadors d’unió (**union**), intersecció (**intersec**) o disjunció (**except**). El resultat serà una altra seqüència on **no** hi haurà elements duplicats.

Anem a utilitzar com a exemple dues seqüències relativament fàcils de construir:

- el nom dels alumnes aprovats (Albert i Joan): //alumne[@aprovat="si"]/nom
- el nom dels alumnes que són delegats (Joan): //alumne[@delegat]/nom

La intersecció ens tornaria els elements que estan en les dues llistes, és a dir 

(//alumne[@aprovat="si"]/nom) intersect (//alumne[@delegat]/nom)

<nom>Joan</nom>

Amb la unió es poden unir les llistes de manera que quede una sola sense duplicats:

(//alumne[@aprovat="si"]/nom) union (//alumne[@delegat]/nom)

<nom>Albert</nom>
<nom>Joan</nom>

I amb la disjunció obtenim els noms de la primera seqüència que no apareixen en la segona: 

(//alumne[@aprovat="si"]/nom) except (//alumne[@delegat]/nom)

<nom>Albert</nom>

**Nota important**

En les seqüències apareixen els **elements** que són **distints**, encara que els seu contingut siga el mateix. Per exemple, el nom del professor és Joan, igual que un dels alumnes. A pesar de tenir el mateix valor, són elements diferents, nodes diferents. Així, en contra del que cabria esperar en principi, si fem la intersecció entre els noms dels alumnes i dels professors, no eixirà cap element .

(//alumne/nom) intersect (//professor/nom)



I si fem la unió de les seqüències anteriors, el nom Joan ens apareixarà 2 vegades, senyal que són elements diferents:

(//alumne/nom) union (//professor/nom)

<nom>Joan</nom>
<nom>Albert</nom>
<nom>Bernat</nom>
<nom>Joan</nom>

[« Anterior](4212__navegaci.md) | [Següent »](4214__funcions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement SenseObraDerivada 4.0](http://creativecommons.org/licenses/by-nd/4.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
