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

[« Anterior](objectius.md) | [Següent »](11_taules.md)
# <a name="main"></a>**Part I: Pràctica inicial**


Aquesta pràctica té la voluntat de servir de repàs del tutorial de Base. Seran una sèrie de exercicis sobre una mateixa Base de Dades, la corresponent a l'exemple amb què s'il·lustra el Tema 2: Model Entitat-Relació. Repetim ací la breu anàlisi de requisits de l' **Empresa**:

1. La companyia està organitzada en departaments. Cadascun té nom únic, número únic i un empleat que el dirigeix. Ens interessa la data en la qual va començar a dirigir-lo.
1. Cada departament controla una sèrie de projectes. Cadascun d'aquestos projectes té nom i número únics, i estarà coordinat per un únic departament.
1. De cada empleat ens interessa el nom (format per dos cognoms i nom de pila), DNI, adreça, telèfon, sou i data de naixement. Tot empleat està assignat a un departament, i moltes vegades tindrà un supervisor. Pot treballar en més d'un projecte (no necessàriament controlats pel mateix departament) i treballarà un determinat número d'hores a la setmana en cada projecte. En un projecte sempre treballarà, com a mínim, un empleat.
1. Volem saber també els familiars de cada empleat, per administrar els termes dels segurs. Volem saber el nom, data de naixement i parentesc amb l'empleat.

L'estructura de les taules és la següent:

![](part_i_prctica_inicial.002.png)

[« Anterior](objectius.md) | [Següent »](11_taules.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
