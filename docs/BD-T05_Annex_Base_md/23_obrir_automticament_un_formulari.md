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

[« Anterior](22_quan_executar_una_macro_esdeveniments.md) | [Següent »](24_exemple_avanat_compliment_de_restriccions_externes.md)
# <a name="main"></a>**2.3 Obrir automàticament un formulari**
Amb la creació del formulari **Menú principal** estem fent una espècie d'aplicació basada en la Base de Dades, de manera que un usuari no expert podria veure i actualitzar la informació a partir dels formularis, i el Mnú principal li permetria navegar per ells.

Per a completar aquesta "aplicació", podríem intentar que en obrir la Base de Dades **Empresa.odb**, automàticament s'obrira el formulari **Menú principal**.

Ho podem aconseguir creant una nova macro per a obrir el formulari **Menú principal**, però no serà tan senzilla com les d'abans, ja quepel moment en què voldrem obrir aquest formulari (al principi, de forma automàtica), ens hem d'assegurar que ja s'ha fet la connexió a aquesta Base de Dades. No podem estar segurs perquè l'estem obrint en aquest moment.

Copieu la següent macro al final del **Module1** de **Empresa.odb**:

Sub obrirMenuPrincipal

`    `If  Not Thisdatabasedocument.currentcontroller.isConnected Then Thisdatabasedocument.currentcontroller.connect

`    `ThisDatabaseDocument.FormDocuments.getbyname("Menú Principal").open

End Sub

I ara, per a que s'execute aquesta macro en obrir **Empresa.odb**, hem d'anar a **Eines -> Personalitza -> pestanya Esdeveniments** , i en l'opció **Obre un document** triar la macro **obrirMenuPrincipal** 

![](23_obrir_automticament_un_formulari.002.png)

[« Anterior](22_quan_executar_una_macro_esdeveniments.md) | [Següent »](24_exemple_avanat_compliment_de_restriccions_externes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
