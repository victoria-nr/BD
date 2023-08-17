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

[« Anterior](part_ii_macros.md) | [Següent »](22_accions_mltiples.md)
# <a name="main"></a>**2.1 Creació d'una Macro**
La manera inicial de crear una macro serà en la barra d'eines **Crear** a la dreta del tot, on hi ha un botó per a crear noves Macros o mòduls.

![ref1]

El que se'ns presentarà per a construir la macro serà el següent:

![ref2]

El següent vídeo mostra tot el procés de creació de la primera macro, ben senzilleta.



Una vegada creada la macro es pot executar amb el botó d'**execució** (si estem editant-la i demanant-nos prèviament que la guardem).

Si ja està guardada, podem executar-la amb l'opció **"*Ejecutar*" del menu emergent** (botó de la dreta sobre el nom de la macro), o senzillament fent **doble-clic** damunt d'ella.

Les coses estaven distribuïdes de forma diferent en Access 2007. Observeu sobretot que els **Noms de macro** (**Submacros**) i **Condicions** (**Si**) estaven dalt, en compte d'estar a la dreta com ara.

![ref3]

![ref2]
## **Exercici 2.1**
En la B.D. de l'empresa, feu la macro de la figura de dalt, però amb el **títol** "**Missatge de salutació**". Guardeu-la amb el nom "**Salutació**" i executeu-la.

Ara ja podrem veure la macro a l'esquerra, en l'apartat de macros. Si no la veieu i esteu segurs que l'heu creada, segurament és perquè Access no està configurat en aquest moment per veure tots els objectes. Trieu l'opció *Todos los objetos de Access* del Pannell d'exploració (el que hi ha a l'esquerra), com us mostra la següent imatge:

![ref4]



Aquesta macro és del tipus **Macro Independent**, que vol dir que no depén de cap altre objecte, i sempre la tindrem disponible.

Com ja es va comentar serà molt normal enllaçar la macro amb algun event. Per exemple quan fem clic a un botó d'un formulari.

![ref2]
## **Exercici 2.2**
Creeu-vos un **formulari nou**, sense utilitzar cap assistent de manera que quede en blanc, sense res. S'aconsegueix anant al botó **Diseño de formulario**. Quan el guardeu li poseu el nom "**Botons**". Afegiu un botó de comando (mireu figura), però de moment sense utilitzar l'assistent ("vareta màgica" desactivada; mireu figura). El que volem és traure el missatge de salutació quan fem clic en el botó. Per aconseguir-ho, aneu a les propietats (botó dret sobre el botó, o tenint-lo seleccionat anar a *Hoja de Propiedades*) a la pestanya "***eventos***", sobre l'esdeveniment "***al hacer clic***" trieu la macro **Salutació**. Per acabar, canvieu el rètol **Comando0** per **Saludar**. Ho podeu fer directament sobre el botó, o canviant la propietat "***Titulo***"

![ref5]

![ref6]

Per a poder comprovar el seu funcionament, haurem "d'executar el formulari", és a dir anar de la "***Vista Diseño***" del Formulari a la "***Vista Formulario***".

Ara anem a crear una **Macro** que **no** serà **Independent**, sinó **associada a un objecte**. Ho aprofitarem per veure una manera més ràpida per fer el procés de creació d'una macro associada a un esdeveniment.

![ref2]
## **Exercici 2.3**
Col·loqueu un altre botó, amb el títol **Despedir**. Aneu a la pestanya d'esdeveniments de les propietat. Però en compte de triar la macro en l'esdeveniment "***al hacer clic***", feu clic als **tres puntets** del costat. Trieu l'opció "***Generador de macros***". Automàticament va a crear-la. Trieu una altra vegada un quadre de missatge (**CuadroDeMensaje**) i poseu el missatge "**Adéu**". Ara tindrem 2 possibilitats de guardar-la.

- Si apretem l'opció de **Guardar como** l'estarem creant com una **Macro independent** (la veurem en l'apartat de Macros del Pannell d'exploració). És possible que en Access 2013 no ens done aquesta possibilitat.
- Si apretem a l'opció de **Guardar** o quan tanquem la Macro contestem afirmativament la pregunta de ***¿Desea guardar los cambios realizados en la macro y actualizar la propiedad?*** l'estarem creant com una **Macro incrustada** en l'objecte actual (que és un botó de comando), i no la veurem en l'apartat de Macros del Pannell d'exploració.

Trieu aquesta segona possibilitat, i veureu com en l'esdeveniment "*al hacer clic*" us posarà **[Macro incrustada]**

Ja hem vist dues maneres d'anar a la creació d'una macro. En veurem una tercera, que serà utilitzant l'assistent. L'assistent ens proposarà que triem una de entre les accions més comunes a l'hora d'utilitzar un botó 

![ref2]
## **Exercici 2.4**
Col·loqueu un tercer botó però activant prèviament l'assistent ("vareta màgica"). Entre les accions possibles que ens proposa, agrupades per categories, triarem "**Ejecutar macro**", del grup "**Otras**". Presentarà les macros independents creades fins el moment. Triem l'única creada fins el moment, **Salutació**. Podeu posar una imatge en el botó, o un comentari. Deixeu la imatge.

El resultat ha estat que l'assistent ha creat una **Macro incrustada** que a la seua vegada executa l'acció **Executar Macro**, concretament la macro **Salutació**. Ho podeu comprovar mirant les propietats del botó.

**Nota**

En versions anteriors a Access 2007, que no existien les macros incrustades, l'assistent el que feia era introduir un procediment en Access Basic (unes quantes instruccions).



Per a editar una macro ja creada: 

- si és una macro **independent** es pot fer des del Pannell d'exploració, apretant amb el botó de la dreta damunt de la macro i triant "*Vista* d*iseño*", o si està associada a algun event d'un control d'un formulari, fent clic als tres puntets del costat.
- si és una macro **incrustada** només ho podrem fer d'aquesta segona manera. 

[« Anterior](part_ii_macros.md) | [Següent »](22_accions_mltiples.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 21_creaci_duna_macro.002.png
[ref2]: 21_creaci_duna_macro.003.png
[ref3]: 21_creaci_duna_macro.004.png
[ref4]: 21_creaci_duna_macro.005.png
[ref5]: 21_creaci_duna_macro.006.png
[ref6]: 21_creaci_duna_macro.007.png
