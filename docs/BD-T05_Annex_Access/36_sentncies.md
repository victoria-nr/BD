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

[« Anterior](35_funcions_i_procediments.md) | [Següent »](37_funcions_estndard.md)
# <a name="main"></a>**3.6 Sentències**
- **Assignació**:

variable = expressió 

- **Condicional**:

IF condició THEN
`     `sentències
`  `[ELSEIF condició THEN
`     `sentències ]
`  `[ELSE
`     `sentències ]
END IF 

- **Condicional múltiple**:

SELECT CASE expressió a comprovar 
`  `CASE llista
`     `sentències
...
`  `[CASE ELSE
`     `sentències ]
END SELECT 

- **Bucle Do ...Loop**

DO [{WHILE | UNTIL} condició]
`     `sentències
LOOP 

DO 
`     `sentències
LOOP [{WHILE | UNTIL} condició] 

- **Bucle For ... Next** 

FOR comptador = valor\_inicial TO valor\_final [ STEP increment]
`     `sentències
NEXT [comptador] 



- **Bucle For Each... Next** 

És una variant del bucle ***For*** que permet que el comptador no siga numèric creixent (o decreixent) sinó que anirà agafant els valors d'una llista, d'un grup (que podrà ser un vector o un altre conjunt, com veurem més avant) 

FOR EACH element IN grup
`     `sentències
NEXT [element] 

- **Bucle While ... Wend**

WHILE condició
`     `sentències
WEND 

En els dos primers bucles tenim la possibilitat de eixir directament (**Exit Do**, **Exit For**) 

- **Executar l'acció d'una macro**: **DoCmd.***nom\_acció\_macro*.

Així per exemple, podem obrir el formulari **Departament** amb 

DoCmd.OpenForm "Departament" 

Es poden fer quasi totes les accions que en les macros (no oblidem de posar-lo en anglès), excepte algunes perquè ja tenen la seua pròpia funció o mètode. 

Les que no es poden fer són: 

**CuadroMsg**: utilitzar directament la funció ***MsgBox***

**EstablecerValor**: utilitzar l'operador **=** per a assignar. 

**DetenerMacro**: no està disponible en Visual Basic. 

**DetenerTodasMacros**: no està disponible en Visual Basic. 

**EjecutarCodigo**: directament posar el nom de la funció o procediment 

**EjecutarAplicación**: utilitzar la funció **Shell**

**EnviarTeclas**: utilitzar directament la funció ***SendKeys***



![ref1]
## **Exercici 3.9**
Proveu la següent funció que trau la taula de multiplicar del 7.  

Function Taula\_7()
`    `Dim i%
`    `Dim s$

`    `s = ""
`    `For i = 1 To 10 Step 1   'si no posem step 1 igual incrementarà en 1
`        `s = s & " 7 x " & i & " = " & 7 \* i & Chr(10)
`    `Next i
`    `MsgBox (s)
End Function 

![ref1]
## **Exercici 3.10**
Fer una funció anomenada **Imparells** que mostre els nombres imparells entre 1 i 50.

Intenteu que el resultat es mostre en una única finestra, per la incomoditat de que mostre cadascun en una finestra (i en són 25). Ho podeu fer separant els numeros per espais en blanc, o baixant de línia (per a anar a una noval línia podeu fer incloure el caràcter de nova línia, que és **chr(10)**), tal i com està en l'exemple de la Taula del 7.

Incloure posteriorment un botó en el formulari Botons que quan s'aprete s'execute la funció anterior.

![ref1]
## **Exercici 3.11 (voluntari)**
Incloure un altre botó en el formulari **Botons** que quan s'aprete s'execute la funció **Sumar()** (situada en el mòdul **Funcions**) la qual ha d'anar demanant números per mig de la funció **inputbox()** i els ha d'anar sumant, fins introduir el 0. Aleshores ha de traure el resultat de la suma.

![ref1]
## **Exercici 3.12**
Copiar el següent procediment, per a provar la sentència **FOR EACH**

Sub vector()
`    `Dim vec(5)
`    `Dim element
`    `vec(0) = 4 + 5
`    `vec(1) = "Hola"
`    `vec(2) = "Adéu"
`    `vec(3) = Date
`    `vec(4) = Time
`    `For Each element In vec
`        `MsgBox (element)
`    `Next element
End Sub 

Observeu que el vector és de 6 elements, i que l'últim element del vector no està inicialitzat, i per tant té el valor nul (per ser tot el vector **Variant**) 

![ref1]
## **Exercici 3.13**
Fer una altra vegada el control sobre el sou major de 4.000 €, però així com abans només s'avisava, ara donarem la possibilitat d'introduir-lo o no.

Per tant substituirem la **macro incrustada** que es va fer en l'**exercici 2.8** per una funció associada a l'**eixida** del control **Sou** (estarà situada en el mòdul associat al formulari **Empleat**).

La funció MsgBox té els següents arguments:

**MsgBox(*comentari,botons\_a\_posar,títol\_finestra,fitxer\_ajuda,context*) As *botó\_cont***

Els botons a posar són constants definides que indiquen quins botons volem que isquen. En el nostre exemple posaríem **vbYesNo**, i la contestació que hem de mirar és **vbNo** (si s'ha apretat el botó de No), on posaríem l'acció **DoCmd.CancelEvent**. És a dir quedaria la condició d'aquesta manera

If MsgBox("Molt alt. Segur que vols el valor " & Sou & " ?", vbYesNo) = vbNo Then

Aneu en compte. El de dalt només s'ha d'executar si el sou és superior a 4.000 €.

[« Anterior](35_funcions_i_procediments.md) | [Següent »](37_funcions_estndard.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 36_sentncies.002.png
