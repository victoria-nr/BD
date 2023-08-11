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

[« Anterior](exercici_42.md) | [Següent »](exercici_43_voluntari_per_puntuable.md)
# <a name="main"></a>**4.2.2 Modificació per a la Base de Dades actual**
Com es comentava al principi d'aquesta Part IV, resulta més complicat modificar la cinta d'opcions de manera que afecte només a la Base de Dades actual.

La manera de definir la cinta canvia radicalment de com es creaven en versions anteriors a Access 2007, les barres i els menús. Ara es definirà en **XML**. Aquest codi XML pot estar guardat en més d'un lloc, definir-lo de més d'una manera. Nosaltres veurem possiblement el lloc més senzill per a col·locar aquest codi XML que definirà la cinta d'opcions. Serà col·locar-la en una taula especial, amb una estructura predeterminada. No intentarem fer un estudi exhaustiu. Ens aconformarem en veure un exemple, i sobre aquest exemple com es podria modificar el codi XML per a modificar la cinta d'opcions.

**Nota**

Al final de la pregunta hi ha un vídeo on es mostra tot el procés



Primer pas: Preparació

Per a poder visulitzar totes les taules, i poder visualitzar possible errors en el moment de crear la cinta d'opcions farem dues preparacions inicials:

**1.- Visualitzar les taules de sistema**

Són taules que utilitza el mateix Access, i per defecte estan ocultes per a no marejar, però ara ens farà falta tenir-les visibles.

Es fa amb el botó de la dreta en l'**explorador d'objectes**, anant a les ***Opciones de navegación***, i activant ***Mostrar objetos del sistema*** 



**2.- Habilitar la presentació dels missatges d'error**

Si quan posem el codi XML hi ha alguna cosa malament ens anirà molt bé que ens mostre quin és l'error. Podem fer que els mostre d'aquesta manera:

Anar al menú **ARCHIVO**, i després anar a les ***Opciones***. En ***Configuración de cliente***, en l'apartat ***General*** haurem d'activar l'opció ***Mostrar errores de interfaz de usuario en el complemento***



Segon pas: Crear la taula del sistema ***USysRibbons***

En la taula **USysRibbon** és on guardarem el codi XML. Obligatòriament ha de tenir la següent estructura:

|**Nom del camp** |**Tipus** |**Grandària** |
| :- | :- | :- |
|ID|Autonumèric|Enter llarg|
|RibbonName|Texto|255|
|RibbonXml|Memo| |

**Nota**

Podeu importar la taula, juntament amb un formulari per a poder visualitzar-la (i modificar-la) còmodament, des de la base de dades adjunta **ribbon.accdb**

Cada fila que introduïm en la taula USysRibbons serà una cinta d'opcions que podrem associar a la nostra aplicació. En **RibbonName** posarem el nom de la cinta, i en **RibbonXml** les diferents opcions de la cinta en format XML. Mirem aquest exemple, que és el que teniu en la Base de Dades **ribbon.accdb**.

![](422_modificaci_per_a_la_base_de_dades_actual.002.png)

Com es pot apreciar , té una estructura jeràrquica, per anar definint la **cinta** (***ribbon***), les **fitxes** (***tab***), els **grups** (***group***) i les **opcions** individuals (***button***). Els elements tindran un camp per a identificar-los (***id***) i en moltes ocasions una etiqueta (***label***) que és la que es mostrarà en la cinta.

Concretament l'element **button**, que defineix les diferents opcions individuals, té entre d'altres els següents camps:

- **id**: identificador que no ha de coincidir amb cap altre.
- **label**: etiqueta que es mostrarà en la cinta
- **imageMSO**: image de la icona d'entre les ja definides que s'associarà a l'opció. Definir una imatge pròpia suposa massa esforç per als objectius d'aquest tema.
- **size**: grandària de la icona, que potser gran (large) o menuda (normal).
- **onAction**: nom de la macro que s'executarà en apretar el botó.
- **supertip**: missatge emergent que eixirà quan ens situem damunt del botó.

Tercer pas: Activar-la

Una vegada creada la taula (que per cert, si ocultem els objectes de sistema també s'amagarà), per a posar-la visible en la nostra aplicació basada en Access, haurem de reiniciar Access o com a mínim la Base de Dades, per a que tinguen efecte els canvis. Aquestos seran els pasos:

1. Tancar la Base de Dades i tornar a obrir-la.
1. Anar a les Opcions d'Access (**botó principal d'Office** -> **Opcions d'Access**), concretament a les opcions de ***Base de datos actual***
1. En l'apartat de ***Opciones de barra de herramientas y de la cinta de opciones*** l'opció ***Nombre de banda de opciones*** és un quadre combinat on ja podrem triar la nostra cinta.
1. Tancar una altra vegada la Base de Dades i tornar a obrir-la.

Per a cada canvi que fem en la cinta (editant la taula USysRibbons) haurem de tancar la BD i tornar a obrir-la, ja que és en aquest moment quan es configura la cinta d'opcions.

En el cas de tenir alguna errada en el codi XML, en el moment d'obrir la Base de Dades ens ho comunicarà.

Resum de tots els passos

En el següent vídeo es realitzen tots els pasos anteriors.

[« Anterior](exercici_42.md) | [Següent »](exercici_43_voluntari_per_puntuable.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
