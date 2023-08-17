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

[« Anterior](31_creaci_dun_mdul.md) | [Següent »](33_tipus_especials.md)
# <a name="main"></a>**3.2 Tipus de dades, Constants i Variables**


Els tipus vàlids de dades són similars als definits en Access. Tindrem més facilitat per a definir-los, i tindrem un tipus molt interessant. Quasi tots els tipus tenen un caràcter que, seguint el nom de la variable, fa que siga d'aquest tipus. Així per a declarar una variable entera podem posar **Dim nom AS Integer**, o senzillament **Dim nom%**. 

|**Tipus de Dades** |**Significat** |**Grandària** |**Caràcter identificador** |
| :- | :- | :- | :- |
|Byte |Enter positiu |1 byte ||
|Integer |Enter |2 bytes |% |
|Long |Enter llarg |4 bytes |& |
|Currency |Enter molt llarg |8 bytes |@ |
|Single |Real simple precisió |4 bytes |! |
|Double |Real doble precisió |8 bytes |# |
|Boolean |True (-1) o False (0) |2 bytes ||
|String |Cadena |1 byte per caràcter |$ |
|Date |Data-Hora |8 bytes ||
|Variant |Variable: qualsevol tipus |1 byte fins 64Kb ||


Especialment interessant és el tipus **VARIANT**, que pot guardar dades de qualsevol tipus. Millor dit, depenent del valor actual funciona com d'un tipus o d'un altre. El següent codi no donaria error: 

Dim v As Variant 
v = 4 
v = v + 2 
v = "Hola" 

El que sí que donaria error seria després 

v = v + 2 

perquè en aquest instant la variable és alfanumèrica. 

![ref1]
## **Exercici 3.4**
Crear una altra funció, en el mateix mòdul d'abans, amb el nom **Prova\_Variant** on estiguen les instruccions anteriors, però després de cadascuna visualitzar el contingut de **v** amb **MsgBox(v)**.

- Per a definir **constants** s'utilitza 

[Global] Const *nom* = *<expressió>*

- Per a definir **variables**

Dim *nom* [AS *tipus*] (per defecte **Variant**) 

- Per a definir **vectors**

Dim *nom* **([*límit\_interior* TO] *límit\_superior*) [AS *tipus*]**

Així per exemple, **DIM v(10) AS Integer** crea un vector de 11 enters (el límit inferior és 0, a no ser que es diga expressament amb la sentència **OPTION BASE 1**, i aleshores l'índex inicial serà 1). 

També es pot alterar l'índex inicial d'aquesta manera: **DIM v(10 TO 20) AS Integer**. També crea un vector de 11 posicions, però el subíndex ha d'anar entre 10 i 20 (sinó donarà un error d'estar fora de rang). 

També es poden definir matrius de dos o més dimensions (fins 60 dimensions). S'hauran d'especificar els límits de cada dimensió separats per comes: **DIM m(5,10)**

- Per a definir variables globals (o vectors globals) poseu **Global** en compte de **Dim**. Aleshores es podrà accedir a la variable des de qualsevol lloc del mòdul. Recordem que hi havia una altra manera de crear una variable global, i que era posar-la dalt de tot, abans de la declaració de la primera funció o procediment. Si una variable no és global, serà **local** i només es pot accedir a ella des del procediment o funció on s'ha creat. La immensa majoria de les variables seran locals. Únicament haurem d'especificar variables globals en casos molt concrets. 

- Per a variables estàtiques (són locals però no volem que es reinicialitzen cada vegada que s'executa el procediment on estan) poseu **Static** en compte de **Dim**.

![ref1]
## **Exercici 3.5**
Per a provar el funcionament d'una variable estàtica, creeu la funció **MissatgeIncrementat** en el mòdul de sempre on es cree una variable estàtica de tipus ***Integer*** sense donar-li un valor inicial (s'iniciarà a 0). Incrementeu-la en una unitat i tragueu un missatge amb el valor de la variable. Proveu a executar unes quantes vegades la funció. Fins i tot inseriu un botó en el formulari **Botons** que execute aquesta funció. Veureu que únicament es reiniciarà quan tanqueu la Base de Dades. 

Registres 

Podem definir estructures pròpies de dades (registres), formades per unes quantes dades individuals que anomenarem camps: 

TYPE nom\_tipus
`    `nom\_camp AS tipus
...
END TYPE

Aquestes estructures s'han de definir al principi del mòdul, en la zona de declaracions, i si estan en un mòdul de Formulari o d'Informe s'ha de posar davant Private. 

La manera d'utilitzar una estructura d'aquestes és definir una variable del tipus, i després utilitzar-la seguida del nom del camp separada per un punt. 

Dim v as nom\_tipus

v.nom\_camp = *valor*
... 



Per exemple, podem definir el tipus anomenat ***Punt*** per a representar les coordenades **x** i **y** d'un pun en el pla. En una funció, primer demanarem les coordenades d'un punt, i després les mostrarem. Per a demanar les dades utilitzem la funció **InputBox**, que obre una finestra on es pot introduir una informació en un quadre de text, i després la funció torna aquesta informació. Recordeu que la definició del tipus (***Type***) ha d'anar dalt de tot. 

Type Punt
`    `x As Integer
`    `y As Integer
End Type

Function Coordenades()
`    `Dim p As Punt

`    `p.x = InputBox("Coordenada x")
`    `p.y = InputBox("Coordenada y")
`    `MsgBox ("(" & p.x & "," & p.y & ")")
End Function 

![ref1]
## **Exercici 3.6 (voluntari)**
Definir el tipus ***Nom*** format per 3 camps: ***Nom\_p***, ***Cognom1*** i ***Cognom2***. Posteriorment crear una altra funció del mateix mòdul, anomenada **Tipus**, on heu de definir una variable del tipus ***Nom***, demanar un valor per a cada camp (per mig de la funció **InputBox**), i després traure-ho tot junt. 

Recordeu que la definició dels tipus ha d'anar al principi del mòdul, en la zona de declaracions 

[« Anterior](31_creaci_dun_mdul.md) | [Següent »](33_tipus_especials.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 32_tipus_de_dades_constants_i_variables.002.png
