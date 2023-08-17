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

[« Anterior](23_submacros.md) | [Següent »](25_resum_daccions.md)
# <a name="main"></a>**2.4 Condicions**
En les macros és d'extremada utilitat exacutar una acció únicament si s'acompleix una condició. Les condicions es posen amb l'acció **Si** (condicional). Com en el cas de les submacros, podem posar el **Si**, tant arrastrant de la dreta, com triant l'acció **Si**. Totes les accions que posem dins del **Si** s'executaran només si s'acompleix la condició.

Des de la versió Access 2010 es pot posar la clàusula **Si no**, que només s'exefcuta si no s'acompleix la condició.

En el següent vídeo es mostra la creació d'una macro amb condició, i posteriorment s'amplia per a posar la part negativa, quan no s'acompleix la condició:

|![ref1]|En Access 20107 la manera de posar condicions era apretant al botó que es veu a l'esquerra. Apareixia una columna nova on es posava la condició, i només en cas que s'acomplira la condició s'executava l'acció de la columna de la dreta.|
| :- | :- |

![ref2]
## **Exercici 2.8**
Crear una macro incrustada en el control **Sou** del Formulari **Empleat** per a traure un missatge d'informació si hem posat un sou molt gran a un empleat (més de 4.000€). 

La condició és **Sou>4000**. 

El moment d'activar és en eixir del control **Sou*** (esdeveniment ***Al Salir***). 

Heu d'observar que traurà el missatge, però no impedirà l'acció. 

**Nota**

**Sou** fa referència al control **Sou** del formulari **Empleat**, no al camp **Sou** de la taula **Empleat**. Podeu comprovar en el formulari Empleat que efectivament el control que fa referència al sou porta aquest nom, i que està lligat amb el camp sou. Però és important saber que fa referència a un control del formulari. Si el formulari no estiguera obert, Access no sabria a que es refereix. Però com que la macro està incrustada en el formulari, no es pot executar si el formulari no està obert. 

![ref2]
## **Exercici 2.9**
Crear una macro independent anomenada **Comprovació data\_n** per a exigir la restricció que la data de naixement d'un empleat no siga posterior a la data actual. I ara sí que intentarem impedir aquesta data.

- Les accions a realitzar podrien ser: traure un missatge i no executar l'event (així si l'event és en **eixir** del control, en cancel·lar-lo ***no eixirem del control**)*. I les dues accions s'han d'executar únicament si s'acompleix la condició. La següent imatge ho il·lustra:

![ref3]

Com podem comprovar si les accions que hem de fer en cas que s'acomplesca la condició són més d'una, han d'anar dins del **Si ... Finalizar si**.

- Si aquesta macro l'executem en **eixir** del component **data\_n** del formulari **Empleat**, anirà quasi sempre bé, però si quan estem editant una data errònia tanquem el formulari, ens eixirà el missatge (i potser més d'una vegada) però la guardarà. Per evitar aquest efecte no desitjat, podríem executar també la macro abans d'actualitzar el registre (és l'esdeveniment **Antes de actualizar** del **formulari**, no del control)

**Nota**

Com que la Macro **Comprovació data\_n** és independent, la podem executar en qualsevol moment. Però com fa referència al control **data\_n** que és un objecte del formulari **Empleat**, si no està obert aquest formulari donarà un error.

En Access 2007, la macro quedarà d'aquesta manera. Observeu que posem les 2 accions en línies diferents, i abans hem de tenir la condició en les 2 files. També valdia posar punts suspensius (...) en la condició de la segona fila, cosa que equival a repetir la condició

![ref4]

En realitat tot açò de la data de naixement ho podríem haver solucionat amb una senzilla regla de validació en el moment de dissenyar la taula. 

Però suposem ara la següent restricció: la data de naixement d'una filla o fill no pot ser posterior a la data de naixement del pare o la mare. Si volem posar aquesta restricció en la taula familiar, no podem posar-la com una regla de validació, perquè afecta valors d'una altra taula (Empleat). Posaríem la macro "***Antes de actualizar***" en el subformulari "**Familiar Subformulario**", fent referència a **[Data\_n]** (data de naixement del familiar) i al control **Data\_n** del formulari "**Empleat-Familiar**". 

![ref2]
## **Exercici 2.10**
Feu l'anterior restricció amb una Macro independent com la de la figura següent. La condició és:

([Parentesc] Como "fill\*") Y ([Data\_n]<=[Formularios].[Empleat-Familiar].[Data\_n])

No us enganyeu amb cap caràcter, perquè sinó Access no ho entendrà. Si us dóna error reviseu el nom de cada objecte (sobretot del formulari Empleat-Familiar).

Tots els elements que no estan qualificats (no porten el nom de l'objecte davant, separat amb un punt) faran referència a objectes del formulari actual, en aquest cas el formulari **Familiar Subformulario**. Si volem fer referència a un altre objecte, haurem de posar on està. Aquesta és la raó d'haver de posar **[Formularios].[Empleat-Familiar].[data\_n]** per a fer referència a aquest element.

Guardeu la macro amb el nom "**Data naixement fills**", i el moment d'executar-la és abans d'actualitzar en el subformulari "**Familiar Subformulario**".

![ref5]

Així és com quedaria en Access 207. Observeu que la segona vegada, en compte de tornar a posar tota la condició, es pot posar "**...**".

![ref6]

![ref2]
## **Eercici 2.11**
En el Tema 3, de Model Relacional, les coses que no podíem representar amb el model, les deixàvem com restriccions externes. L'única manera de fer-les efectives seria amb Macros i per mig de programes (Mòduls) de Visual Basic.

Feu complir la següent restricció amb una macro independent, anomenada **Control projectes**:

**El número total de projectes treballats per un treballador no ha de ser major que 4.**

El moment de controlar serà abans d'actualitzar un registre en la taula TREBALLA, per tant com en els casos anteriors, haurem controlar l'esdeveniment del formulari **Treballa** anomenat ***Antes de actualizar***.

S'haurà d'utilitzar la funció **DCont** per a comptar els projectes en els quals està treballant, i tenir en compte que el que s'està introduint encara no està introduït del tot. Aquesta funció té 3 paràmetres: el primer el camp que volem comptar (un que no estiga buit, per exemple **[dni]**; el segon és l'àmbit de recerca, que en el nostre cas és la taula **Treballa**; el tercer és un criteri per a seleccionar les files (si no posem res se comptaran totes les files), que en el nostre cas seria **[dni]=[Formularios].[Treballa].[Cuadro\_combinado0]**.

Aneu amb compte amb el nom del control on es col·loca el *dni* en el formulari **Treballa**. En el meu cas s'anomena **Cuadro\_combinado0**, però potser vosaltres no tingueu el mateix nom.

Aquesta seria la condició (en el meu cas):

DCont("[num\_p]";"Treballa";"[dni]=[Formularios].[Treballa].[Cuadro\_combinado0]")+1>4

I així quedaria la macro

![ref7]

Per a poder comprovar el funcionament de la macro, podeu intentar introduir una nova fila (cuideu que siga nova, no modifiqueu una fila anterior), per mig del formulari **Treballa**, amb les segünets dades:

- Pilar Folch Mestre (18932165)
- Auditoria ordinària
- 7 hores

Com que Pilar Folch ja estava treballant en 4 projectes, treballar en aquest altre passaria de 4 projectes, i per tant hauria de donar error (la macro cancelaria l'event).

En el cas d'Access 2007 quedaria: 

![ref8]



[« Anterior](23_submacros.md) | [Següent »](25_resum_daccions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 24_condicions.002.png
[ref2]: 24_condicions.003.png
[ref3]: 24_condicions.004.png
[ref4]: 24_condicions.005.png
[ref5]: 24_condicions.006.png
[ref6]: 24_condicions.007.png
[ref7]: 24_condicions.008.png
[ref8]: 24_condicions.009.png
