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

[« Anterior](part_i_prctica_inicial.md) | [Següent »](12_consultes.md)
# <a name="main"></a>**1.1 Taules**


Realitzar les següents qüestions:

**1.1)** Crear una BD en blanc amb el nom **Empresa.accdb**

**1.2)** Importar **EMPLEAT** i **DEPARTAMENT** de la Base de Dades **OrEmpresa.accdb** que es proporciona. El següent vídeo us explica com fer la importació 

**1.3**) Importar una taula a partir del fitxer XML **Familiar.xml**

Durant la importació haurem de cuidar els següents aspectes:

- La clau principal ha de ser **Dni + Nom**
- El camp **Data\_n** ha de ser de tipus **Fecha/Hora**

El següent vídeo us explica com fer la importació: 

**1.4)** Importar una taula a partir del fitxer de text **PROJECTE.txt**,

Durant la importació haurem de cuidar els següents aspectes:

**Num\_p** : ha de ser numèric i que ocupe un **byte**. Ha de ser **clau principal**.

**Nom\_p** : (no res)

**Departament** : numèric **byte**, i el seu valor no pot ser nul (açò últim ho haureu de fer després de la importació)

El següent vídeo us explica com fer la importació: 

**1.5)** Dissenyar la taula **TREBALLA** (observeu l'esquema Relacional per veure la seua estructura). Els camps seran **dni**, **num\_p** i **hores**. Els tipus de **dni** i **num\_p** venen condicionats per ser claus externes. L'atribut **hores** (de tipus numèric menudet) ha de ser no nul, i major que zero (i per tant el seu valor predeterminat no convé que siga zero). No us oblideu de la clau principal.

**1.6)** Crear **totes** les integritats referencials. Recordeu que la integritat referencial obliga que la clau externa agafe un dels valors ja introduïts de la clau principal on apunta (així per exemple, la fletxa que apunta des del camp ***Departament*** de la taula **EMPLEAT** fins el camp ***Num\_d*** de la taula **DEPARTAMENT** obliga a posar a cada empleat un departament vàlid, és a dir, dels existents en l'actualitat). A més les de **FAMILIAR** i **TREBALLA** han de modificar i esborrar en ***cascada***.

Segurament la més "complicada" de fer és la reflexiva que marca els supervisors. Per a poder representar-la, en Access s'ha de posar la taula (en aquest cas **EMPLEAT**) 2 vegades i s'arrastra d'una a l'altra. No és que siguen 2 taules, sinó que s'afegeix a les relacions 2 vegades, però és la mateixa taula.

**1.7)** Dissenyar un **formulari** anomenat **Treballa** per a introduir les dades a aquesta taula. Els atributs **Dni** i **Num\_p** s'introduiran per mig de ***quadres combinats***, on es visualitzaran respectivament **Dni - Nom** i **Num\_p - Nom\_p**. L'atribut Hores s'introduirà per mig d'un quadre de text.

El següent vídeo explica com crear aquest formulari. La dificultat consisteix en definir bé els quadres combinats. Per a poder explicar-lo millor, el primer quadre combinat es crea utilitzant l'assistent de quadre combinat. Després intenta estudiar les propietats més útils. El segon quadre combinat es crea més "a pèl", modificant les propietats més importants.


Introduïu a continuació les següents dades. Observeu que entre parèntesi està el Dni de l'empleat i el número de projecte, però únicament a nivell informatiu. No ha d'aparéixer en el quadre combinat.



|**"dni"**|**"Num\_p"**|**hores**|
| :- | :- | :- |
|Llopis Bernat, Jaume (18876543)|Auditoria 98 (2)|10|
|Folch Mestre, Pilar (18932165)|Auditoria 98 (2)|5|
|Peris Andreu, Joan (18933333)|Programa comptabilitat (3)|10|
|Sebastià Broch, Ferran (18934567)|Programa comptabilitat (3)|20|
|Garrido Vidal, Rosa (18900111)|Control vendes (4)|5|
|Nebot Aliaga, Carme (18922222)|Control vendes (4)|25|
|Folch Mestre, Pilar (18932165)|Control vendes (4)|5|
|Garcia Tomàs, Alícia (18944444)|Control vendes (4)|15|
|Garrido Vidal, Rosa (18900111)|Recopilació dades (5)|15|
|Folch Mestre, Pilar (18932165)|Anàlisi estadística (6)|5|
|Sebastià Broch, Ferran (18934567)|Anàlisi estadística (6)|10|
|Llopis Bernat, Jaume (18876543)|Estudi rendiment (7)|5|
|Folch Mestre, Pilar (18932165)|Estudi rendiment (7)|15|
|Garcia Tomàs, Alícia (18944444)|Estudi rendiment (7)|5|



Però ¿com estaran introduïdes de veritat les dades? ¿Estarà el nom o el Dni? Les dades "reals" les veurem sempre en la taula (en aquest cas **TREBALLA**)

[« Anterior](part_i_prctica_inicial.md) | [Següent »](12_consultes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
