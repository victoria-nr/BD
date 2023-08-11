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

[« Anterior](part_iii_mduls_visual_basic.md) | [Següent »](32_tipus_de_dades_constants_i_variables.md)
# <a name="main"></a>**3.1 Creació d'un Mòdul**


Per a crear un **procediment** en un **mòdul estàndard**, primer s'haurà de crear el mòdul com s'indica en la següent imatge.

![ref1]



Per a visualitzar el **mòdul associat** a un **formulari** o **informe** haurem d'estar en la vista disseny del formulari o informe, i haurem d'apretar en el botonet que hi ha dalt a la dreta (***Ver código***).


![ref2]

En realitat quan està en marxa Access està també en marxa l'**editor** de **Visual Basic**. Podem alternar entre Access i aquest editor amb **Alt-F11**.

Quan creem un mòdul, del tipus que siga, ens apareixerà l'editor de Visual Basic, que té el següent aspecte:

![ref3]

Per a inserir les funcions o procediments podem triar el botó adequat (ens preguntarà pel nom i si volem que siga una funció o un procediment) o directament començar a escriure **Function *nom*()** o **Sub *nom*()**. Automàticament, en veure que és un nova funció o procediment, posarà una ratlla separadora i també **End Function** o **End Sub**, segons el cas.

Si volem poder utilitzar una variable des de qualsevol funció o procediment del mòdul (s'anomena variable **global**) l'haurem de col·locar al principi, abans de la declaració de la primera funció o procediment.

Per a executar, podem fer clic en el botó d'executar, estant situats en les línies de la funció.

![ref2]
## **Exercici 3.1**

Crear la següent funció **Data\_avui** en un mòdul estàndard nou que després anomenarem **Funcions**.

![ref4]

Podeu comprovar com aquest entorn ofereix molt ajuda "en línia", mentre anem escrivint les sentències. Pot servir fins i tot per a comprovar que la sintaxi de les instruccions i de les funcions és correcta.

El que fa la funció és traure la data d'avui (funció ***Date***), amb un determinat format. Hi ha molts caràcters que tenen significat per a la funció ***Format***, com són **d** per al dia (en distints formats), **m** per al mes, **y** per a l'any... 
Si volem traure algun d'aquestos caràcters "especials", haurem d'utilitzar davant el caràcter d'escape: **\**

Podeu consultar més informació en l'ajuda d'Access (***F1***).

Quan acabeu apreteu al botó de guardar, i us dirà de guardar Módulo1. Poseu-li el nom de **Funcions**

![ref2]
## **Exercici 3.2**
Exercici 3.2 

Col·locar un altre botó en el formulari **Botons** de manera que s'execute aquesta funció. 

En les propietats, en l'esdeveniment "***Al hacer clic***", s'haurà de posar **=Data\_avui()** (no us oblideu de posar el signe igual) 

![ref2]
## **Exercici 3.3**
Una altra manera d'executar la funció és per mig d'una macro. 

Crear una macro independent anomenada **M\_Data\_Avui** que execute la funció **Data\_avui**(). L'acció que s'ha d'executar en la macro serà **EjecutarCódigo**. 

[« Anterior](part_iii_mduls_visual_basic.md) | [Següent »](32_tipus_de_dades_constants_i_variables.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 31_creaci_dun_mdul.002.png
[ref2]: 31_creaci_dun_mdul.003.png
[ref3]: 31_creaci_dun_mdul.004.png
[ref4]: 31_creaci_dun_mdul.005.png
