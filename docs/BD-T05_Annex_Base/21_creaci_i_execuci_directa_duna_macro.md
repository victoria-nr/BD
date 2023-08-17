Bases de Dades

- [Tema 5 (annex): Base avançat](index.md)
- [Objectius](objectius.md)
- [Part I: Pràctica inicial](part_i_prctica_inicial.md) 
  - [1.1 Taules](11_taules.md)
  - [1.2 Consultes](12_consultes.md)
  - [1.3 Formularis i Informes](13_formularis_i_informes.md)
- [Part II: Macros (Voluntari)](part_ii_macros_voluntari.md) 
  - [2.1 Creació i execució directa d'una Macro](21_creaci_i_execuci_directa_duna_macro.md)
  - [2.2 Quan executar una macro: esdeveniments](22_quan_executar_una_macro_esdeveniments.md)
  - [2.3 Obrir automàticament un formulari](23_obrir_automticament_un_formulari.md)
  - [2.4 Exemple avançat: compliment de restriccions externes](24_exemple_avanat_compliment_de_restriccions_externes.md)

[« Anterior](part_ii_macros_voluntari.md) | [Següent »](22_quan_executar_una_macro_esdeveniments.md)
# <a name="main"></a>**2.1 Creació i execució directa d'una Macro**
La manera inicial de crear una macro serà en el menú  **Eines -> Macros -> Organitza les macros -> Basic**

![ref1]

(després de la primera vegada podrem anar un poc més directament amb **Eines -> Macros -> Edita les macros** )

El que se'ns presentarà per a organitzar les macros serà el següent:

![ref2]

Però el lloc on vol col·locar les macros seria un lloc personal (les meves macros). Millor col·locar les macros en la mateixa Base de Dades, que en el nostre exemple és **Empresa.odb**. Així, si copiem la Base de Dades, les macros viatjaran amb ella. Per tant, ens situem en **Empresa.odb** i apretem al botó **Crea**:

![ref3]

En preguntarà per un nom de mòdul, on van tots els procediments de les macros. El nom que ens proposa **Module1** ens va bé.

Se'ns obrirà una finestra on podem observar que està esperant a que escriguem el codi dels procediments en què consistiran les macros

![ref4]

Anem a crear una macro molt senzilleta, per a saludar, escrivint senzillament la sentència **print("Hola")** dins del procediment (**Sub**). Aprofitem per a canviar el nom del procediment a **Saludar** en compte de **Main**, i després apretem el botó de play (o F5) per a executar-la. Així ens quedarà la cosa:

![ref5]

Aquesta macro s'haurà executat de forma directa sense problemes. Però per a poder executar les macros no de forma directa sinó en resposta a un esdeveniment, haurem de baixar la seguretat i permetre l'execució de macros.

Es fa en el menú **Eines -> Opcions -> Seguretat -> Seguretat de les macros**, i triar la seguretat més baixa, en la qual sí que permetrem l'execució

![ref6]

Ara anem a crear una **Macro** que **no** serà **Independent**, sinó **associada a un objecte**. Ho aprofitarem per veure una manera més ràpida per fer el procés de creació d'una macro associada a un esdeveniment.

[« Anterior](part_ii_macros_voluntari.md) | [Següent »](22_quan_executar_una_macro_esdeveniments.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 21_creaci_i_execuci_directa_duna_macro.002.png
[ref2]: 21_creaci_i_execuci_directa_duna_macro.003.png
[ref3]: 21_creaci_i_execuci_directa_duna_macro.004.png
[ref4]: 21_creaci_i_execuci_directa_duna_macro.005.png
[ref5]: 21_creaci_i_execuci_directa_duna_macro.006.png
[ref6]: 21_creaci_i_execuci_directa_duna_macro.007.png
