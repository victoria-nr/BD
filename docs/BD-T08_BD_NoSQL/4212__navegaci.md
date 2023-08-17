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

[« Anterior](4211__vista_darbre.md) | [Següent »](4213__seqncies.md)
# **4.2.1.2 - Navegació**
Com que la representació interna del document XML per XPath serà un arbre, es pot navegar per ell especificant camins d’una manera semblant a com es fa en els directoris dels sistemes operatius.

El més important per tenir en compte a l’hora de crear una expressió XPath és saber quin és el node en el qual està situat el procés (**node de context**), ja que és des d’aquest que s’avaluarà l’expressió. El node de context al principi és el node arrel però es va movent a mesura que es van avaluant les expressions, i per tant podem expressar els camins XPath de dues maneres:

- **Camins absoluts**
- **Camins relatius**

Els **camins absoluts** són camins que sempre comencen en l’arrel de l’arbre. Es poden identificar perquè el primer caràcter de l’expressió sempre serà l’arrel ”**/**”. No importa quin siga el node de context si es fan servir camins absoluts, perquè el resultat sempre serà el mateix.

En canvi, els **camins relatius** parteixen des del node en el qual estem situats.

Per exemple, es pot obtenir el node **<nom>** del professor de l’exemple anterior fent servir l’expressió XPath següent:

/classe/professor/nom

Podem veure com s’avalua l’expressió en l’arbre XPath en la següent figura, marcat el camí en taronja:

![ref1]

Observeu que el resultat d’aquesta expressió no és només el contingut de l’element sinó tot l’element **<nom>**.

<nom>Joan</nom>

Mai no s’ha d’oblidar que l’expressió sempre intenta aconseguir el nombre màxim de camins correctes i, per tant, no necessàriament ha de retornar només un únic valor. Per exemple, si l’expressió per avaluar és la següent:

/classe/alumnes/alumne/nom

XPath l’avaluaria intentant aconseguir tots els camins que quadren amb l’expressió, tal com podeu veure visualment en la següent figura:

![ref1]

i per tant els resultats són (observeu que Joan es refereix al nom del tercer alumne, no del professor):

<nom>Albert</nom>

<nom>Bernat</nom>

<nom>Joan</nom>

A pesar que en els exemples anteriors sempre s’han retornat nodes finals això no necessàriament ha de ser així, ja que XPath pot retornar qualsevol tipus d’element com a resultat.

/classe/alumnes

La navegació per l’arbre no difereix massa dels altres casos:

![ref1]

En aquest cas el resultat no és un element simple sinó que és tot un subarbre d’elements.

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

Si se sap que una expressió retornarà més d'un resultat però només se’n vol un d’específic, es pot fer servir un número envoltat per claudàtors quadrats ”**[ ]**” per indicar quin és el que es vol aconseguir. Per retornar només el primer alumne podeu fer el següent:

/classe/alumnes/alumne[1]

que tornarà el següent:

<alumne aprovat="si">

<nom>Albert</nom>

<cognoms>Alegre</cognoms>

<nota>6</nota>

</alumne>

ja que dels tres nodes disponibles com a fills de **<alumnes>**, només se seleccionarà el primer:

![ref1]

Es poden fer servir els claudàtors en qualsevol lloc de l’expressió per fer determinar quina de les branques es triarà. Per exemple, es pot obtenir només el **nom** del segon alumne amb una expressió com aquesta:

/classe/alumnes/alumne[2]/nom

<nom>Bernat</nom>

Sempre s’ha d’anar amb compte en escriure les expressions XPath, ja que si el camí especificat no es correspon amb un camí **real** dins de l’arbre no es retornarà cap resultat.

/classe/nom

Com que en arribar al node **classe** no n’hi trobarà cap d’anomenat **<nom>**, no retornarà cap resultat, com podeu veure si seguiu l’arbre:

![ref1]

Obtenir els atributs d'un element

Els valors dels atributs es poden aconseguir especificant el símbol **@** davant del nom de l'atribut, quan s’haja arribat a l’element que el conté:

`  `/classe/professor/@Especialitat

` `![ref1]



S’ha de tenir en compte que a diferència del que passa amb els elements, en obtenir un atribut no tindrem un element sinó només el seu valor: 

` `507

` `**Nota**

Depenent de l'entorn en què ens trobem, podria ser que l'anterior no ens mostre res. La raó és perquè els atributs no es poden serialitzar, i per tant no es poden mostrar en un entorn de XML. No tindríem aquest problema si accedim des de Java. La manera de solucionar-lo des de l'entorn de eXist és utilitzar la funció **data()**:

/classe/professor/data(@Especialitat)

Obtenir el contingut d'un element

Per a aquells casos en què només vulguem el contingut de l’element, s’ha definit la funció **text()** per obtenir aquest contingut. Això s’ha fet així perquè d’altra manera, com que els nodes de text no tenen nom, no s’hi podria accedir.

De manera que si a un element que tinga contingut de dades se li afegeix ***text()***: 

`  `/classe/professor/nom/text()

…retornarà el contingut del node sense les etiquetes: 

`  `Joan



Comodins

De la mateixa manera que en els sistemes operatius, es poden fer servir comodins diversos en les expressions XPath. Es poden veure els comodins en la taula següent.

|**Comodí**|**Significat**|
| :-: | :-: |
|\*|L’asterisc es fa servir per indicar tots els elements d’un determinat nivell.|
|.|Com en els directoris dels sistemes operatius el punt serveix per indicar el node actual.|
|..|Es fa servir per indicar el pare del node en el qual estem.|
|//|La doble barra indica que quadrarà amb qualsevol cosa des del node en el qual estem, es a dir que buscarà en tots els seus descendents. Pot ser un sol element o un arbre de nodes.|

Amb l’asterisc es poden obtenir tots els elements d’un determinat nivell. Amb aquesta expressió es poden obtenir tots els elements de dins del node **professor**.

/classe/professor/\*

Aquesta expressió retornarà per separat els dos nodes fills de **<professor>** , **<nom>** i **<cognom>.**

<nom>Joan</nom>

<cognoms>Puig</cognoms>

O bé fer servir les dobles barres (**//**) per obtenir tots els elements **<nom>** del fitxer independentment del lloc on estiguen dins del document XML.

//nom

El resultat serà:

<nom>Joan</nom>

<nom>Albert</nom>

<nom>Bernat</nom>

<nom>Joan</nom>

Observeu que apareix el nom Joan 2 vegades, ja que és tant el nom del professor com d'un dels alumnes

**Nota**

En realitat aquesta sentència XPath tornarà molts més resultats, ja que buscarà en tots els documents de la col·lecció, i en **Rutes.xml** hi ha molts elements **nom**: els noms de les rutes i els noms dels punts, a banda dels noms de professors i d'alumnes.

Es poden posar les dobles barres en qualsevol lloc dins de l’expressió per indicar que pot haver qualsevol cosa enmig a partir del lloc on apareguen.

/classe/alumnes//nom

Donarà els dos noms dels alumnes (ara sí només alumnes, ni professors ni noms de ruta ni de punts):

<nom>Albert</nom>

<nom>Bernat</nom>

<nom>Joan</nom>

Tot i que facilita molt la creació d’expressions no és molt recomanable abusar del comodí **//** per motius d’eficiència. Les expressions amb aquest comodí requeriran molts més càlculs per ser avaluades, i per tant les expressions tardaran més a donar resultats. 



Eixos XPATH

Per avaluar les expressions XPath s’explora un arbre, de manera que també es proporcionen una sèrie d’elements per fer referència a parts de l’arbre. Aquestos elements s’anomenen **eixos XPath**

|**Eix**|**Significat**|
| :-: | :-: |
|**self::**|El node en el qual està el procés (fa el mateix que el punt)|
|**child::**|Fill de l’element actual|
|**parent::**|El pare de l’element actual (idèntic a fer servir ..)|
|**attribute::**|Es fa servir per obtenir un atribut de l’element actual (@)|

Alguns d’aquestos eixos pràcticament no es fan servir perquè generalment és més còmode i curt definir les expressions a partir del símbol. Tothom prefereix fer servir una expressió com aquesta:

/classe/professor/nom

Que no la seua versió equivalent fent servir els eixos:

/child::classe/child::professor/child::nom

A part dels vistos en la taula anterior n’hi ha d’altres, que en aquest cas no tenen cap símbol que els simplifique:

|**Eix**|**Significat**|
| :-: | :-: |
|**descendant::**|Tots els descendents del node actual|
|**desdendant-or-self::**|El node actual i els seus descendents|
|**ancestor::**|Els ascendents del node|
|**ancestor-or-self::**|El node actual i els seus ascendents|
|**preceding::**||

**This document was truncated here because it was created in the Evaluation Mode.**
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 4212__navegaci.002.png
