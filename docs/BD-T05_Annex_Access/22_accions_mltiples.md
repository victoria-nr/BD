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

[« Anterior](21_creaci_duna_macro.md) | [Següent »](23_submacros.md)
# <a name="main"></a>**2.2 Accions múltiples**


Es pot especificar més d'una acció en una macro. Només s'han de posar en línies consecutives (apretem a **+ Agregar nueva accion** que hi ha baix de l'acció anterior), i s'executaran en l'ordre definit.

Per exemple podem modificar la macro **Salutació** per a que mostre desprès del missatge "***Hola***" un altre missatge: "***Què tal?***". I podem fer al principi de la macro que mostre un rellotge d'arena en el cursor (l'acció és **MostrarCursorDeRelojDeArena**, i en versions anterior es deia senzillament **RelojDeArena**). Observeu que per a recol·locar les accions tenim les fletxes verdes de pujar i baixar a la dreta de cada acció.

![ref1]
## **Exercici 2.5**
Col·locar un altre botó amb el títol **Tancar** per a tancar el formulari "***Botons***", avisant primer que es va a tancar per mig d'un quadre de missatge que diga "Va a tancar-se aquest formulari". L'acció de tancar es diu "***CerrarVentana***", i si no s'especifica res, tancarà l'objecte actual (el formulari actual). La macro ha de ser **independent** i s'ha de dir **Tancar**.

![ref1]
## **Exercici 2.6**
- Crear un formulari per a Empleat (l'únic que ens queda), per mig de l'opció "**Autoformulario**", que en Access 2013 es fa *seleccionant* la taula Empleat i anant a **Crear** → **Formulario**. Deixeu-lo amb el nom **Empleat**.
- Crear un nou formulari (en blanc) anomenat "**Menú Principal**". Posar un botó de **tancar** el formulari com el de l'exercici anterior, aprofitant la mateixa macro, ja que és independent.
- Crear un altre botó per anar al formulari "**Empleat**". L'acció serà "**AbrirFormulario**" i evidentment en els paràmetres s'ha de posar (o triar) el nom del formulari que volem obrir: **Empleat**. La macro ha de ser independent, i s'ha d'anomenar "**Obrir Formularis**".
- Crear 4 botons més, que posteriorment serviran per a anar a tots els formularis. L'aspecte podria ser aquest

![ref2]

**Nota**

El paràmetre **Modo de la ventana** indica de quina manera s'obrirà el formulari (en aquest cas **Empleat**). Les més interessants són:

- **Normal**: obrirà el formulari en una nova pestanya. Podem tornar a l'original (Menú principal) i anar alternant entre les pestanyes obertes.
- **Diàleg**: obrirà el formulari en una finestra, i fins que no la tanquem (en aquest cas el formulari Empleat) no podrem fer res més en Access

Anem a triar el mode **Diàleg**, encara que en el punt següent es tornarà a plantejar el tema.

**Nota**

Aquest exercici no utilitza realment accions múltiples. És senzillament un exercici de preparació per al que ve després.

[« Anterior](21_creaci_duna_macro.md) | [Següent »](23_submacros.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 22_accions_mltiples.002.png
[ref2]: 22_accions_mltiples.003.png
