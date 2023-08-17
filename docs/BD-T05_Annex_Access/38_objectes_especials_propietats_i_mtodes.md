Bases de Dades

- [Tema 5 (annex): Access avançat](index.md)
- [Objectius](objectius.md)
- [Part I: Pràctica inicial](part_i_prctica_inicial.md) 
  - [1.1 Taules](11_taules.md)
  - [1.2 Consultes](12_consultes.md)
  - [1.3 Formularis i Informes](13_formularis_i_informes.md)
- [Part II: Macros](part_ii_macros.md) 
  - [2.1 Creació d'una Macro](21_creaci_duna_macro.md)
  - [2.2 Accions múltiples](22_accions_mltiples.md)
  - [2.3 Submacros](23_submacros.md)
  - [2.4 Condicions](24_condicions.md)
  - [2.5 Resum d'accions](25_resum_daccions.md)
  - [2.6 Resum d'esdeveniments](26_resum_desdeveniments.md)
- [Part III: Mòduls (Visual Basic)](part_iii_mduls_visual_basic.md) 
  - [3.1 Creació d'un Mòdul](31_creaci_dun_mdul.md)
  - [3.2 Tipus de dades, Constants i Variables](32_tipus_de_dades_constants_i_variables.md)
  - [3.3 Tipus especials](33_tipus_especials.md)
  - [3.4 Operadors](34_operadors.md)
  - [3.5 Funcions i Procediments](35_funcions_i_procediments.md)
  - [3.6 Sentències](36_sentncies.md)
  - [3.7 Funcions estàndard](37_funcions_estndard.md)
  - [3.8 Objectes especials: propietats i mètodes](38_objectes_especials_propietats_i_mtodes.md)
- [Part IV: Configurar l'aspecte](part_iv_configurar_laspecte.md) 
  - [4.1 Configurar la Barra d'Accés ràpid](41_configurar_la_barra_daccs_rpid.md) 
    - [Exercici 4.1](exercici_41.md)
  - [4.2 La cinta d'opcions](42_la_cinta_dopcions.md) 
    - [4.2.1 Modificació per a tot Access](421_modificaci_per_a_tot_access.md) 
      - [Exercici 4.2](exercici_42.md)
    - [4.2.2 Modificació per a la Base de Dades actual](422_modificaci_per_a_la_base_de_dades_actual.md) 
      - [Exercici 4.3 (voluntari però puntuable)](exercici_43_voluntari_per_puntuable.md)
  - [4.3 El panell de navegació](43_el_panell_de_navegaci.md)
  - [4.4 Opcions d'aplicació](44_opcions_daplicaci.md) 
    - [Exercici 4.4](exercici_44.md)
  - [4.5 El panell de control](45_el_panell_de_control.md) 
    - [Exercici 4.5](exercici_45.md)

[« Anterior](37_funcions_estndard.md) | [Següent »](part_iv_configurar_laspecte.md)
# <a name="main"></a>**3.8 Objectes especials: propietats i mètodes**


Visual Basic és un llenguatge de programació orientat a objectes. Els objectes són un conjunt de dades i de procediments (en POO els procediments d'un objecte s'anomenen **mètodes**). La manera d'especificar un camp de l'objecte o un mètode és similar: *nom\_objecte.nom\_camp\_o\_procediment.*

Dels objectes ja definits en VBA anem a veure 2 que utilitzarem especialment. 

**Nota Important**

Aquestos objectes pertanyen a la col·lecció d'objectes **DAO** (*Data Access Objects*). Depenent de la configuració particular de l'Access, podria ser que aquestos objectes no estigueren disponibles en primera instància.  Per a que estiguen disponibles hauríem d'anar dis de l'editor de Visual Basic a ***Herramientas → Referencias***  i activar ***Microsoft DAO 3.6 Object Library*** o una similar. 

DataBase 

És un objecte que fa referència a una Base de Dades. 

Operacions: 

- **Set** *variable\_BD* **= CurrentDB** *per a que apunte a l'actual Base de Dades*

- **Set** *variable\_BD* **= nothing** *per a que no apunte a res*

**Nota**

Es pot fer que apunte a altres Bases de Dades que no siguen l'actual, però resulta més complicat d'estructurar. Per als objectius d'aquest curs tenim prou amb la Base de Dades actual (**CurrentDB**) 

- **OpenRecordSet**(*origen, mode*) 

L'origen pot ser una taula, una consulta o una sentència SQL. 

El mode indica el mode d'obertura, només lectura, lectura-escriptura, ... 

RecordSet 

És un objecte que fa referència a un conjunt de registres 

Operacions: 

- **Set** *variable\_RS* **=** *variable\_BD*.OpenRecordSet(*origen, mode*) 

- **Close**: per a tancar el RecordSet. 

- Mètodes **Move**, per a desplaçar entre els registres: **MoveFirst, MoveLast, MoveNext, MovePrevious**. 

- Mètodes **Find**, per a localitzar registres: **FindFirst, FindNext, FindPrevious, ...**

- **Delete**, per a esborrar el registre actual. 

- Modificació, on s'hauria de preparar primer, fer la modificació al camp, i actualitzar 

*Nom\_RS*.Edit 
*Nom\_rs*!*nom\_camp*=*valor* 
*Nom\_RS*.Update 

- Inserció de registres, on també s'has de preparar primer, posar els valors als camps i per últim actualitzar: 

*Nom\_RS*.AddNew 
*Nom\_rs*!*nom\_camp\_1*=*valor\_1* 
*...* 
*Nom\_rs*!*nom\_camp\_n*=*valor\_n* 
*Nom\_RS*.Update 

- **RecordCount**: compta el nombre de registres del RecordSet (és convenient fer primer un MoveLast, per a recòrrer prèviament tot el RecorSet). 

- **BOF, EOF**: propietats que indiquen respectivament principi i final de fitxer.



![ref1]
## **Exercici 3.15**
Treure el nom de tots els empleats en una única finestra. Servirà per veure com recòrrer un recordset des del principi fins el final. Anirem acumulant els noms dels empleats en una variable (amb el caràcter de baixar de línia), per a mostrar al final aquesta variable. 

Sub Noms\_Empleats()
`    `Dim bd As Database
`    `Dim rs As Recordset
`    `Dim s As String

`    `Set bd = CurrentDb
`    `Set rs = bd.OpenRecordset("Empleat")
`    `rs.MoveFirst
`    `s = ""
`    `While Not rs.EOF
`        `s = s & rs!Nom & Chr(10)
`        `rs.MoveNext
`    `Wend
`    `MsgBox (s)
End Sub 

![ref1]
## **Exercici 3.16 (voluntari)**
Col·locar un botó en **Menú Principal** anomenat **Pujada selectiva**, que demane una quantitat (serà el que es pujarà als empleats) i després que vaja preguntant si es puja el sou a cadascun dels empleats. Només en el cas de contestar afirmativament s'ha de pujar (en cas contrari es deixa igual). La **funció** ha d'estar en el mòdul estàndard **Funcions**, i s'ha d'anomenar **Pujada\_selectiva**. 

![ref1]
## **Exercici 3.17**
Posar un botó en el formulari **Treballa** anomenat **Nou Projecte**, de manera que aniríem al formulari **Projecte per a introduir-ne un nou**. És convenient obrir-lo en Mode *diàleg* (***acDialog***). 

Quan tornem de la introducció del projecte s'haurà d'actualitzar la llista de projectes del quadre combinat **Num\_p** (però observeu el nom que teniu en el vostre formulari Treballa). Es fa per mig d'un mètode del quadre combinat anomenat ***Requery***, que torna a executar la consulta interna que omple la llista. 

També estaria bé que aquest quadre combinat estiguera seleccionat i que es desplegara automàticament la llista adjunta (mètodes **SetFocus** i **DropDown** respectivament). 

![ref1]
## **Exercici 3.18 (voluntari)**
Fer acomplir la restricció externa que diu: 

**RexR1**: El cap d'un departament ha de ser membre d'aquest 

Per no complicar-nos la vida, ho farem en el formulari **Departament**, i en el quadre combinat on se selecciona el director, només traure els membres del departament (per tant, només heu de canviar la consulta associada al quadre combinat). 

Tindrem una complicació, i és que quan s'executa la consulta que dóna els noms dels empleats del departament, se selaccionaran els del primer departament. Quan anem al següent registre, continuarem amb la mateixa llista. Solució: cada vegada que canviem de registre ("***Al activar registro***") obligar a fer una altra vegada la consulta. Com hem vist en l'exercici anterior, això és un mètode del mateix quadre combinat: ***Director.Requery*** (si és que ***Director*** és el nom del quadre combinat). 

[« Anterior](37_funcions_estndard.md) | [Següent »](part_iv_configurar_laspecte.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 38_objectes_especials_propietats_i_mtodes.002.png
