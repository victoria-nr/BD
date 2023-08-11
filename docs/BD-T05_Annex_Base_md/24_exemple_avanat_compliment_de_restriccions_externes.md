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

[« Anterior](23_obrir_automticament_un_formulari.md)
# <a name="main"></a>**2.4 Exemple avançat: compliment de restriccions externes**
Podem utilitzar les macros per a aconseguir alguna de les restriccions externes del Model Relacional, ja que per mig del codi podem aconseguir coses molt potents.

Per exemple, en l'esquema del Model Relacional havíem apuntat aquesta restricció externa:

**Rex1: El cap d'un departament ha de ser membre d'aquest**

Com podríem aconseguir açò? Doncs si en el formulari **Departament** en el quadre de llista que havíem fet per a triar el director, només mostrem els membres del Departament que s'està visualitzant, ho tindríem prou bé per a acomplir la restricció. Està clar que no ho aconseguirem sempre, ja que si anem a editar les dades en la taula directament, ens ho saltarem. Però és una primera manera d'aconseguir-ho. En el Tema 7, ho podrem fer de manera més seriosa.

Copieu el següent codi al costat de les altres macros que havíem fet. Evidentment, aquesta macro ja és molt avançada, molt més dels objectius introductoris d'aquest annex. Per tant, agafeu-la únicament com un exemple. 

Sub DirectorDepartament

`    `form\_container = ThisDatabaseDocument.FormDocuments.getByName("DEPARTAMENT")

`    `form\_container.open

`    `formDepartament = form\_container.Component.getDrawPage().getForms().getByIndex(0)

`    `campDepartament = formDepartament.getByName("fmtnum\_d")

`    `departament = campDepartament.getCurrentValue

`    `sSql = "SELECT ""nom"" , ""dni"" FROM ""EMPLEAT""" &\_

`			`" WHERE ""departament"" = '" & departament & "' ORDER BY ""nom"" ASC"

`    `director = formDepartament.getByName("txtdirector")

`    `director.listsource = array(sSql)

`    `director.refresh()

End Sub

En definitiva el que fem és agafar el valor que té el camp **num\_d** del formulari **Departament**, i fer una sentència SQL seleccionant els empleats d'aquest departament. Això li ho assignem al camp **director**, i el **refresquem** per a que ens ho mostre en aquest mateix moment.

Falta saber el moment en què hem d'executar aquesta macro. Haurà de ser cada vegada que ens situem en un nou registre de la taula Departament. Aquest esdeveniment s'anomena **Després del canvi de registre**, i és un esdeveniment del mateix **formulari**, no de cap control. En ell triarem la macro que acabem de copiar, que es diu **DirectorDepartament**

![ref1]

Quan executem el formulari, podem observar que en el quadre de llista només estan els empleats del present departament

![ref2]

[« Anterior](23_obrir_automticament_un_formulari.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 24_exemple_avanat_compliment_de_restriccions_externes.002.png
[ref2]: 24_exemple_avanat_compliment_de_restriccions_externes.003.png
