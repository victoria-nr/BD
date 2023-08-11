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

[« Anterior](25_resum_daccions.md) | [Següent »](part_iii_mduls_visual_basic.md)
# <a name="main"></a>**2.6 Resum d'esdeveniments**
Serviran per a executar, quan es produesca l'esdeveniment, una macro o un procediment d'Access Basic. A continuació va una relació d'alguns d'ells, amb l'instant en què es produeixen.

|**Esdeveniment** |**Moment en què es produeix**|
| :- | :- |
|Al abrir|Quan s'obre un formulari o informe, però abans de visualitzar el primer registre|
|Al cargar|Després d'obrir i visualitzar els registres (*no es pot cancel·lar*)|
|Al cambiar el tamaño|Després de carregar, i cada vegada que es canvie la grandària de la finestra del formulari o informe|
|Al activar|Quan la finestra passa a ser l'activa (potser en l'aplicació tinguem més d'una finestra oberta en un moment donat)|
|Al desactivar|Quan la finestra deixa de ser l'activa.|
|Al descargar|Quan es tanca un formulari o informe, però abans que s'esborre de la pantalla.|
|Al cerrar|Quan es tanca el formulari o informe (*no es pot cancel·lar*)|
|Antes de actualizar|Abans que els canvis efectuats en el control o en el formulari es guarden en la B.D.|
|Después de actualizar|Després d'actualitzar les dades. No es pot cancel·lar, però sí desfer.|
|Antes de insertar|Quan es comença a introduir el primer caràcter d'una fila nova.|
|Después de insertar|Quan ja s'ha inserit la fila nova.|
|Al eliminar|Just abans d'eliminar la fila|
|Antes de confirmar eliminación|Després d'eliminar, però abans de visualitzar-se la finestra de confirmació d'eliminació.|
|Después de confirmar eliminación|Després d'eliminar i confirmar l'eliminació.|
|Al activar registro|Quan se selecciona un nou registre, però abans de visualitzar-lo.|
|Al cambiar|Sempre que es canvie el contingut del quadre de text o quadre combinat|
|Al no estar en la lista|Si s'introdueix un valor en un quadre combinat que no està en la llista associada.|
|Al entrar, Al salir|Respectivament quan el control passa a ser l'actiu i quan deixa de ser.|
|Al hacer clic, Al hacer doble clic|Quan es fa un clic (baixar el botó del ratolí i tornar a pujar-lo) o dos seguits.|
|Al bajar el mouse, Al subir el mouse|Quan apretem un botó del ratolí i quan l'amollem (respectivament)|
|Al mover el mouse|Quan es meneja el ratolí per damunt del control o formulari. No cal tenir algun botó apretat.|
|Al presionar una tecla|Quan s'aprete (i s'acaba d'apretar) una tecla o combinació de tecles.|
|Al bajar una tecla|Quan s'aprete una tecla|
|Al subir una tecla|Quan es deixa d'apretar|

![ref1]
## **Exercici 2.19**
Per a provar l'ordre en què es produeixen tots els events relacionats amb l'obertura d'un formulari, feu que isca un comentari a cadascun d'ells: ***Al abrir***: obrint; ***Al cargar***: Carregant; ***Al cambiar tamaño***: canviant grandària; ***Al activar***: activant. Feu-lo sobre el formulari **Botons**, i tot amb macros incrustades.

Feu el mateix amb els relacionats amb la tancada. 

![ref1]
## **Exercici 2.20 (voluntari)**
En el formulari "**Empleat**" tenim un botó per anar als familiars de l'empleat (i només d'ell). Estaria molt bé que si l'empleat no té familiars, doncs que no es puga anar a veure'ls fent que no aparega el botó, o encara millor, deshabilitant-lo, de manera que no es puga fer clic.

Feu-la com una macro independent anomenada **Vis\_Familiars**.

El moment on activar la macro és ***Al activar registro***, ja que és quan se situa en el nou registre.

La manera de saber si té o no familiars és comptar-los amb la funció **DCont**, ja utilitzada en l'exercici 2.11. És una funció un poc llandosa, que ha de tenir la sintaxi exacta per a que funcione. La manera de comptar els familiars del present empleat és:

DCont("[Dni]";"Familiar";"[dni]=[Formularios].[Empleat].[dni]")

**Nota**

Podeu tenir l'efecte "col·lateral" que si desactiveu el botó quan tinguem un empleat sense familiars, ja no aparega actiu quan anem a un que sí que es té.

Haureu de fer, per tant, dues accions:

- Si no en té → desactivar el botó
- Si sí que en té → activar el botó

[« Anterior](25_resum_daccions.md) | [Següent »](part_iii_mduls_visual_basic.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 26_resum_desdeveniments.002.png
