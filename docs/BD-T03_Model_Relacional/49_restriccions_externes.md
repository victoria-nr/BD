Bases de Dades

- [Tema 3: Model Relacional](index.md)
- [Objectius i coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. Estructura del Model Relacional](2_estructura_del_model_relacional.md)
- [3. Restriccions](3_restriccions.md) 
  - [3.1 Restriccions inherents](31_restriccions_inherents.md)
  - [3.2 Restriccions d'usuari](32_restriccions_dusuari.md) 
    - [3.2.1 Restricció de domini](321_restricci_de_domini.md)
    - [3.2.2 Restricció de clau principal](322_restricci_de_clau_principal.md)
    - [3.2.3 Restricció d'unicitat](323_restricci_dunicitat.md)
    - [3.2.4 Restricció de valor no nul](324_restricci_de_valor_no_nul.md)
    - [3.2.5 Integritat referencial](325_integritat_referencial.md)
    - [3.2.6 Restriccions externes](326_restriccions_externes.md)
- [4. Tranformació del M. E/R al M. Relacional](4_tranformaci_del_m_er_al_m_relacional.md) 
  - [4.1 Entitats](41_entitats.md)
  - [4.2 Relacions 1:N](42_relacions_1n.md)
  - [4.3 Relacions M:N](43_relacions_mn.md)
  - [4.4 Relacions 1:1](44_relacions_11.md)
  - [4.5 Entitats dèbils](45_entitats_dbils.md)
  - [4.6 Resum dependències](46_resum_dependncies.md)
  - [4.7 Relacions ternàries](47_relacions_ternries.md)
  - [4.8 Especialitzacions](48_especialitzacions.md)
  - [4.9 Restriccions externes](49_restriccions_externes.md)
  - [4.10 Exemple](410_exemple.md)
- [5. Llenguatges relacionals](5_llenguatges_relacionals.md)
- [6. Exercicis](6_exercicis.md)
- [Auto-avaluació](autoavaluaci.md)

[« Anterior](48_especialitzacions.md) | [Següent »](410_exemple.md)
# <a name="main"></a>**4.9 Restriccions externes**


Ja hem comentat que restriccions externes són restriccions que no es poden expressar per mig del model de dades. Aleshores les expressarem de paraula. 

Normalment, les restriccions externes del Model E/R continuaran sent-ho en el Model Relacional, perquè tampoc es podran expressar. En el nostre exemple teníem les restriccions externes del Model E/R: 

**Rex1**: El cap d'un departament ha de ser membre d'aquest. 

**Rex2**: Un empleat només pot treballar en projectes coordinats pel seu departament. 

Açò tampoc es pot expressar amb el Model Relacional, per tant les mantindrem. 

A banda, es poden crear més restriccions externes, perquè amb el Model Relacional no es pot expressar tot el que es podia expressar amb el Model E/R. Per exemple, en la relació: 

![ref1]

ja hem comentat que donarà lloc, a banda de les taules de les entitats, a una altra taula: 

![ref2]

on **dni** i **num\_p** són claus externes. Però l'entitat projecte participa de forma total en la relació, és a dir, en tot projecte ha d'haver un empleat treballant. ¿Com ho controlem això? Doncs és una nova restricció externa que la podríem formular així: 

**RexR3**: Tot projecte ha de tenir com a mínim un empleat treballant-hi. 

Les participacions totals que ens suposaran una restricció externa són: 

- En una relació **1:N**, una participació total de l'entitat que participa amb grau 1.

- En una relació **M:N**, qualsevol participació total (si les dues participen de forma total, aleshores hi haurà dues restriccions externes).

- En una relació **1:1**, depèn de la manera de traduir-se.

La manera d'implementar les restriccions externes serà per mig d'un TRIGGER, que s'active quan hi haja una actualització (inserció, modificació o esborrat) que afecte a la restricció externa. Per exemple, en la restricció **RexR3** els moments importants són després d'inserir un nou projecte, i abans d'eliminar o modificar en la taula **Treballa** (per si un projecte es queda sense gent treballant en ell). 

Les accions a desenvolupar podrien ser traure un avís, o obligar a inserir com a mínim una tupla en la taula **Treballa**, en el cas de la inserció d'un nou projecte; en el cas de modificació o eliminació en **Treballa** podria impedir-se aquesta actualització. 



En el nostre exemple tindrem les restriccions externes al Model Relacional: 

**RexR1**: El cap d'un departament ha de ser membre d'aquest. 

**RexR2**: Un empleat només pot treballar en projectes coordinats pel seu departament. 

**RexR3**: Tot projecte ha de tenir com a mínim un empleat treballant-hi. 



[« Anterior](48_especialitzacions.md) | [Següent »](410_exemple.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 49_restriccions_externes.002.png
[ref2]: 49_restriccions_externes.003.png
