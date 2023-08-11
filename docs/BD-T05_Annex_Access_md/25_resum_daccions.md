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

[« Anterior](24_condicions.md) | [Següent »](26_resum_desdeveniments.md)
# <a name="main"></a>**2.5 Resum d'accions**
A continuació farem un resum de les accions més comuns que es poden incorporar en les macros d'Access. Quan utilitzem l'assistent en inserir un botó, quasi totes les accions que ens proposa l'assistent estaran en aquesta llista. Les agruparem segons la funció:



Obrir i tancar Objectes

<table><tr><th valign="top"><b>Acció</b></th><th colspan="2" valign="top"><b>Comentari</b></th></tr>
<tr><td valign="top">AbrirTabla</td><td colspan="2" rowspan="5"><p>Per a obrir qualsevol d'aquestos objectes en qualsevol dels seus formats: disseny, full de càlcul, formulari, ...</p><p>En formularis i informes es pot, a més, definir un filtre.</p></td></tr>
<tr><td valign="top">AbrirConsulta</td></tr>
<tr><td valign="top">AbrirFormulario</td></tr>
<tr><td valign="top">AbrirInforme</td></tr>
<tr><td>AbrirModuloVisualBasic</td></tr>
<tr><td valign="top">CerrarVentana</td><td colspan="2" valign="top">Per a tancar qualsevol objecte. Si no s'especifica quin, es tancarà l'objecte actiu</td></tr>
</table>
**Nota**

Si no es veu alguna d'aquestes accions de macro (com per exemple **AbrirModuloVisualBasic**), activeu el botó **Mostrar todas las acciones**

![ref1]
## **Exercici 2.12**
Col·locar dos botons en "**Menú Principal**" per a obrir els dos ***informes*** existents en la Base de Dades **Empresa**. Feu-lo per mig de una macro independent anomenada **Obrir Informes** que contindrà dos submacros: **Obrir Informe** i **Obrir Etiquetes**.

Els podeu obrir en "**Vista Preliminar**", per veure millor com queda l'informe.



Col·locar un altre botó per a obrir el gràfic dels projectes: **Projectes - Gràfic d'hores**. Feu-lo per mig d'una macro independent anomenada **Obrir Grafic**. La millor manera per obrir el gràfic és amb la vista "**GráficoDinámico**".

![ref1]
## **Exercici 2.13 (voluntari)**
Modifiqueu la consulta "**13: Augment de Sou**", per generalitzar-la i que demane per teclat el departament al qual se li augmenta el sou, i el percentatge. És a dir, el departament i l'augment (del qual hem d'introduir una quantitat numèrica, que serà agafada com un percentatge) seran dos **paràmetres**. Recordeu que els paràmetres es posen entre claudàtors (**[ ]**) i no han de coincidir amb cap camp de les taules de la consulta. D'aquesta manera, Access ens demanarà un valor per a aquestos paràmetres.

Posteriorment col·loqueu un altre botó en "**Menú Principal**" per a obrir aquesta consulta (per mig d'una macro incrustada).

![ref1]
## **Exercici 2.14**
Intentarem col·locar un botó en el formulari "**Empleat**" per anar als seus familiars. La idea serà obrir el Formulari "**Empleat-Familiar**", però aplicant un filtre, és a dir que només es vegen els familiars de l'empleat actiu en el formulari "**Empleat**". De moment utilitzarem l'assistent quan col·loquem el botó "***Familiar***" en el formulari "**Empleat**". L'acció que voldrem serà obrir un formulari, però quan arriben a la següent pantalla:

![ref2]

Haurem de triar la primera opció, equivalent a aplicar un filtre. La condició d'aquest filtre és que ha de coincidir el **Dni**, i per a aconseguir-ho triem els dos Dni de les dues columnes i apretem al botó **<->**:

![ref3]

I a la següent pantalla podem triar un text o una imatge per al botó. Trieu un text, per exemple **Familiars**.

El que ha fet l'assistent és crear una macro incrustada.

En Access 2007 no funcionaria com esperàvem, i en compte de visualitzar-se en el formulari **Empleat-Familiar** únicament l'empleat que teníem en el formulari **Empleat**, es veurien tots. Es pot arreglar tenint en comte el següent exercici.

![ref1]
## **Exercici 2.15**
Ara ho farem el mateix procés per mig d'una macro independent creada per nosaltres, per a ser més conscient del que fem.

Col·loqueu un altre botó, aquesta vegada sense l'assistent, per anar als Projectes en els quals treballa aquest empleat. Generarem una nova macro, anomenada "**Projectes d'un empleat**", en la qual obrirem el formulari "**Treballa**" però posant la següent condició en "***Condicion WHERE***"

dni=Formularios.Empleat.dni

D'aquesta manera obliguem a que el camp **Dni** de **Treballa** coincidisca amb el contingut del control **dni** situat en el formulari "**Empleat**".



Segurament haurà funcionat bé. I hi ha una diferència en el moment de crear la condició. En la macro incrustada en el botó d'anar als familiars, tindrem en la ***Condicion WHERE*** :

"[Dni]=" & "'" & [Dni] & "'"

Açò podria ser ambigu, i de fet en Access 2007 no funcionaria, ja que Dni podria no saber a qui es refereix, si al control del formulari **Empleat-Familiar** o al control del formulari **Empleat**. En canvi en la nostra macro (creada per nosaltres) no hem deixat lloc a l'ambigüitat, i en el cas d'Access 2007 seria la manera de solucionar  el problema:

dni=Formularios.Empleat.dni

Execucions i parades

|CancelarEvento|Cancel·la l'event que ha provocar aquesta macro. Si és abans d'actulitzar, no l'actualitza, si és abans d'eixir no eixirà, ...|
| :- | :- |
|DetenerMacro|Finalitza l'execució de la present macro.|
|DetenerTodasMacros|Finalitza la present macro i totes aquelles a les quals pot cridar.|
|EjecutarSQL|Executa una sentència SQL de manipulació (inserció, esborrat, ...)|
|EjecutarCódigo|Executa un procediment o funció de VBA (*Visual Basic for Applications*).|
|EjecutarMacro|Executa una altra macro.|
|EjecutarAplicación|Executa un programa executable extern a Access.|
|EjecutarComandoDeMenú|Executa una de les accions definides en els menús estàndar d'Access|
|SalirDeAccess|Tanca Access|

![ref1]
## **Exercici 2.16**
Canvieu la macro "**Tancar**", i en compte de l'acció "**Cerrar**", poseu "**Salir**". Després de comprovar l'efecte, torneu a deixar-la com estava. Però observeu com serà molt útil en aplicacions completes destinades a usuaris no experts. 

Recerca de dades i desplaçament

|IrRegistro|Es desplaça a un determinat registre. Es pot triar: anar al primer, anar a l'anterior, anar al següent, anar a l'últim o anar a un registre determinat.|
| :- | :- |
|BuscarRegistro|Buscar un registre que acomplesca unes condicions.|
|BuscarRegistroSiguiente|Busca el següent que acompleix les condicions.|

![ref1]
## **Exercici 2.17**
Crear dos botons de navegació per al formulari "**Projecte**": un per anar al següent registre ( > ) i un altre per anar a l'anterior ( < ). Les dues macros associades, que poden ser incrustades, utilitzaran l'acció "***IrARegistro***".

No aniran del tot bé, ja que al final i al principi, si anem més enllà dels registres que tenim, pot donar problemes. Però de moment tenim suficient.

Altres

|DefinirPropiedad|Canvia el valor d'una propietat d'un control d'un formulari o informe. Pot servir per exemple per a fer visible un control, posant a -1 (vertader) la propietat **Visible**.|
| :- | :- |
|EstablecerValor|Canvia el valor de qualsevol control o qualsevol propietat. També pot servir per a fer visible un control: en *elemento* ***Boton1.Visible***; i en *expresión **True***.|
|NuevaConsulta|Actualitza les dades d'un control que depèn d'una consulta (un quadre combinat, un subformulari, ...)|
|EnviarTeclas|Guarda en la memòria intermitja de teclat les tecles especificades.|
|IrAControl|Activa el control especificat.|
|MostrarCursorDeRelojDeArena|Mostra el rellotge d'arena mentre es va executant la macro.|
|MaximizarVentana, MinimizarVentana|Maximitza i minimitza, respectivament, la finestra activa.|
|RestaurarVentana|Restaura una finestra maximitzada o minimitzada a la grandària anterior.|
|Bip|Emet un so.|
|CuadroDeMensaje|Presenta un missatge.|
|Imprimir|Imprimeix l'objecte|
|ExportarConFormato|Trau l'eixida cap a un fitxer Excel, Word o de text.|
|ImportarExportarDatos|Importa o exporta dades des de o cap a B.D. externes d'altres tipus.|

Recordeu que si no es veu alguna de les accions abans esmentades, és perquè no està activat el botó **Mostrar todas las acciones**

![ref1]
## **Exercici 2.18 (voluntari)**
Posar dos botons en el formulari "**Botons**" anomenats **Boto1** i **Boto2**, de manera que quan s'aprete el primer es visualitze el segon i es deixe de visualitzar el primer, i a l'inrevés. Heu de ser conscients que s'ha de fer més d'una acció: quan punxem en un botó, aquest és l'actiu, i si l'intentem fer-lo invisible ens donarà un error perquè no es pot deixar de visualitzar un control que "*tiene el enfoque*" Per tant les accions seran en aquest ordre:

- Fer visible l'altre Botó (propietat **Visible** de l'altre botó a **True**)
- Passar el control a l'altre botó (**IrAControl**)
- Per últim fer invisible aquest botó (propietat **Visible** d'aquest botó a **False**)

[« Anterior](24_condicions.md) | [Següent »](26_resum_desdeveniments.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 25_resum_daccions.002.png
[ref2]: 25_resum_daccions.003.png
[ref3]: 25_resum_daccions.004.png
