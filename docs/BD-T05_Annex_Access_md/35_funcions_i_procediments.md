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

[« Anterior](34_operadors.md) | [Següent »](36_sentncies.md)
# <a name="main"></a>**3.5 Funcions i Procediments**


FUNCIONS 

Les sentències per definir una funció són 

[STATIC][PUBLIC|PRIVATE] FUNCTION nom\_funció ([p1 [AS tipus], ...]) [AS tipus\_funció]
`                                 `(sentències de la funció)
`                                 `[nom\_funció = expressió]
END FUNCTION



Com s'observa potser duga paràmetres o potser no, i podem definir de quin tipus és la funció (el tipus que tornarà) o no. 

Si es declara **STATIC** totes les variables locals seran estàtiques (és a dir, conservaran el valor entre cridades) 

Si es declara **PUBLIC** (que és l'opció per defecte) la funció estarà disponible des de qualsevol lloc, qualsevol mòdul de la Base de Dades 

Si es declara **PRIVATE** la funció només estarà disponible des del mòdul on està declarada. 

PROCEDIMENTS 

Un procediment és molt paregut, excepte que no torna un valor 

[STATIC][PUBLIC | PRIVATE] SUB nom\_subrutina ([arg1 [AS tipus], ...])
`                                   `(sentències del procediment)
END SUB



Encara que les funcions i els procediments es poden executar directament (com ho estem fent fins ara), o cridant-los directament en resposta a un event (com en l'exercici 3.2), moltes vegades es cridaran des d'altres mòduls. 

Per a cridar una funció o procediment és suficient posar el seu nom o **Call** i el seu nom. Recordeu que si és una funció que torna un valor, aquest es podrà assignar, posar en una expressió, ... 



![](35_funcions_i_procediments.002.png)
## **Exercici 3.8**
Provar a declarar la funció de l'**exercici 3.5**, **MissatgeIncrementat()**, com a **Private**. Intentar utilitzar-la apretant el botó del formulari **Botons**. Després deixar-la com estava. 

[« Anterior](34_operadors.md) | [Següent »](36_sentncies.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
