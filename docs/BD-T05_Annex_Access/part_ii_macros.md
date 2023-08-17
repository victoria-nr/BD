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

[« Anterior](13_formularis_i_informes.md) | [Següent »](21_creaci_duna_macro.md)
# <a name="main"></a>**Part II: Macros**


Una **macro** és una seqüència ordenada d'accions que s'executa bé expressament, bé en resposta a un esdeveniment ("event") com la pulsació amb el ratolí, o una tecla, o quan es carrega un formulari, etc.

- Les accions que es poden executar són molt variades: obrir un altre formulari o informe, localitzar un registre, treure un missatge, afegir o eliminar registres, etc. En la penúltima pregunta d'aquesta part es veu un resum de les accions que es poden incorporar en una macro.
- I el moment en el qual es poden executar, els esdeveniments, també és molt variat. En l'última pregunta es fa un resum dels esdeveniments, en resposta dels quals es pot executar una macro.

Tant les macros com els mòduls de programa en Visual Basic serveixen per al mateix objectiu. La diferència entre utilitzar una cosa o l'altra és la senzillesa i la potència. Les macros seran més senzilles i ràpides de realitzar (sobretot per a usuaris no experts). Els mòduls de VBA, que és el Visual Basic incorporat en Access, són més potents ja que per mig de programa podrem fer qualsevol cosa, però més incòmodes de fer per als no familiaritzats en Visual Basic.

A partir del Access 2007 les macros poden estar situades en dos llocs.

- Com a objectes **independents**
- Associades a un control o un Formulari o Informe, aleshores es diu que estan **incrustades**

En versions anteriors només estaven les Macros independents.

Encara que en **Access 2013** les macros funcionen bàsicament igual que en **Access 2007** (que és quan van canviar molt respecte versions anteriors, incorporant les macros incrustades), l'aspecte sí que canvia canvia un poc. Per això conservaré algunes imatges d'Access 2007, comparant-les amb les d'Access 2013.

[« Anterior](13_formularis_i_informes.md) | [Següent »](21_creaci_duna_macro.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
