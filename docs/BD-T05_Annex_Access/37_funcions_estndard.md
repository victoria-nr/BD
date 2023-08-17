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

[« Anterior](36_sentncies.md) | [Següent »](38_objectes_especials_propietats_i_mtodes.md)
# <a name="main"></a>**3.7 Funcions estàndard**


A continuació veurem algunes de les funcions que ens proporciona VBA agrupades per categories 

FUNCIONS MATEMÀTIQUES 

|**Abs(*n*)**: valor absolut de *n*|**Cos(*r*)**: cosinus |
| :- | :- |
|**Exp(*n*)**: el número ***e*** elevat a una potència |**Hex(*n*)**: Converteix a hexadecimal |
|**Int(*r*)**: part entera de *r*|**Log(*r*)**: logaritme en base ***e*** de *r* |
|**Oct(*n*)**: converteix a octal |**Randomize(*n*)**: inicialitza el generador de números aleatoris |
|**Rnd()**: número aleatori entre 0 i 1 |**Sin(*r*)**: sinus |
|**Tan(*n*)**: tangent | |



FUNCIONS DE CONVERSIÓ 

|Convertir a un determinat tipus |**CBool, CByte, CCur, CDate, CDbl, Cdec, CInt, CLng, CSng, CStr, CVar, CVErr** |
| :- | :- |



FUNCIONS DE TRACTAMENT DE CADENA 

(Nota: Hi ha moltes funcions que poden o no dur un $ al final: la versió que no en porta torna un valor **Variant**, mentre que la que sí que en duu torna un **String**) 

|**Asc(*text*)**|Codi ASCII del primer caràcter |
| :- | :- |
|**Chr(*n*)**|Torna el caràcter corresponent al codi ASCII *n*|
|**Format(*text*,*format*)**|Torna el valor amb el format indicat |
|**InStr(*i,cadena*,*subcadena*)**|Torna la posició en la qual es troba la subcadena dins de la cadena (si no la troba, 0), començant des de la posició *i*|
|**Lcase(*text*)**|Passa a minúscules |
|**Left(*text*,*n*)**|Torna *n* caràcters del costat esquerre |
|**Len(*text*)**|Llargària de la cadena |
|**Ltrim(*text*)**|Elimina els espais en blanc de l'esquerra |
|**Mid(*text*,*i*,*n*)** |Torna *n* caràcters, començant des de la posició *i*. Si no s'especifica *n* és fins el final de la cadena |
|**Right(*text*,*n*)**|Torna *n* caràcters del costat dret |
|**Rtrim(*text*)**|Elimina els espais en blanc de la dreta |
|**Space(*n*)**|Torna una cadena amb el número de espais en blanc especificat |
|**Str(*n*)**|Converteix un número en una cadena |
|**StrComp(*text1*,*text2*)**|Compara dues cadenes (els caràcters ASCII). Es pot fer que distingisca majúscules i minúscules, o que no ho faça |
|**String(*n*,*c*)**|Torna una cadena amb el caràcter *c* repetit *n* vegades |
|**Trim(*text*)**|Elimina els espais en blanc dels dos costats |
|**Ucase(*text*)**|Passa a majúscules |
|**Val(*text*)**|Converteix una cadena en un número |



FUNCIONS DE DATA I HORA 

|**Now**: dia i hora del sistema |**Date**: dia del sistema |
| :- | :- |
|**Time**: hora del sistema | |
|**Day**: trau el dia d'una data |**Month**: trau el mes d'una data |
|**Weekday**: trau el dia de la setmana (diumenge 1, dilluns 2, ...)|**Year**: trau l'any d'una data |
|**Hour**: trau l'hora |**Minute**: trau els minuts |
|**Second**: trau els segons | |
|**DateDiff**: diferència entre dues dates (en el format especificat: dies, mesos, ...) |**DateAdd**: suma a una data un número determinat de espais temporals (dies, ...) |



FUNCIONS D'AGREGAT 

Totes aquestes funcions treballen sobre un conjunt de valors, de files tretes d'alguna taula. Sempre tindran 3 arguments: 

- **Expresión**: indica el camp que es busca, sobre el qual es vol fer alguna cosa.
- **Dominio**: indica la nom de la taula o consulta d'on es trauen les dades.
- **Criterio**: indica una possible selecció de les files de la taula.

|**DAvg**: calcula la mitjana |**DCount**: compta quantes files |
| :- | :- |
|**DLookup**: torna el valor del camp de la primera fila que satisfa el criteri |**DFirst**: torna el primer valor del camp especificat |
|**DLast**: torna l'últim |**DMin**: valor mínim |
|**DMax**:** valor màxim |**DStDev**: desviació típica |
|**DSum**: suma |**DVar**: variància |

Nota: Aquestes funcions les veurem bé en el tema de SQL. 



ALTRES FUNCIONS 

|**InputBox**|Quadre de entrada. Torna un **String**. El format de la funció és: <br>**InputBox(missatge[, títol][, valor per defecte][, xpos][, ypos][, helpfile, context])**|
| :- | :- |
|**MsgBox**|Finestra de missatge. Es poden especificar els botons que apareixeran i la funció torna un valor que equival al botó apretat <br>**MsgBox(missatge[, botons][, títol][, helpfile, context])**|

![ref1]
## **Exercici 3.14 (voluntari)**

Per mig de les funcions de cadena intentar traure, en una **etiqueta nova** en el formulari **Empleat**, els noms dels empleats canviant l'ordre (nom + cognoms). Feu-lo progressivament així:

- Primer l'intenteu traure amb el mateix format que està, és a dir *Cognoms, Nom* 
- Després intenteu-lo amb el format de la figura: nom i cognoms. Es tractarà de trobar la **coma** (amb **InStr()** ) 
  - Traure primer el que hi ha darrere de la coma (pot anar molt bé la funció **Mid**, ja que pot traure fins el final de la cadena).
  - Després el que hi ha davant, i segurament la funció més còmoda serà **Left()**.
  - Per complicar-lo un poc més, podríem traure els **cognoms** en **majúscules**.

La propietat de l'etiqueta que s'ha de modificar és **Caption**. Haureu de mirar el nom que us dóna per a l'etiqueta, que pot canviar d'uns a una altres.

Aquest seria l'aspecte:

![ref2]

El moment oportú podria ser "***Al activar registro***". Com que alguns de vosaltres tindreu una macro per aquest event (realitzada en l'exercici 2.20, que era voluntari), podeu substituir-la pel procediment (que pot esat associat al formulari), i dins d'aquest cridar la macro amb:

DoCmd.RunMacro "*nom\_de\_la\_macro*"

Així es es faran les dues feines, la de l'exercici 2.20 i la d'aquest exercici.

[« Anterior](36_sentncies.md) | [Següent »](38_objectes_especials_propietats_i_mtodes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 37_funcions_estndard.002.png
[ref2]: 37_funcions_estndard.003.png
