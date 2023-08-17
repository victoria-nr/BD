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

[« Anterior](322_restricci_de_clau_principal.md) | [Següent »](324_restricci_de_valor_no_nul.md)
# <a name="main"></a>**3.2.3 Restricció d'unicitat**


Si en un camp, o en un conjunt de camps, definim la restricció d'unicitat (**UNIQUE**), això obliga a que, en cas de tenir valors el camp, no es puguen repetir. Suposem, per exemple, els alumnes d'un Institut. La clau no pot ser el DNI, ja que alguns alumnes no en tindran, però en cas de tenir-ne, és clar que no es podrà repetir.

Representarem que un camp és únic, posant **únic** entre parèntesi baix del camp. Per exemple, si considerem que el camp nom de la taula EMPLEAT ha de ser únic, ho representarem així:

EMPLEAT (dni, nom, adreca, telefon, sou, data\_n) 

(únic)



En **Access** la restricció d'unicitat (**UNIQUE**)** es defineix posant en l'apartat ***Indexado*** el valor ***Sí (sin duplicados)***. En la figura es mostra com fer que el camp **nom** de la taula **EMPLEAT** siga únic.

![ref1]

En **Base** de **LibreOffice** es fa creant un índex, en el símbol   ![ref2]

Haurem crear un nou índex, el camp pel qual volem l'índex, l'ordre que ens interessa (normalment ascendent) i **deixar activa la casella Únic**

![ref3]

En aquesta imatge es veu com pel fet d'haver creat la clau principal, ja s'havia creat un índex, en la imatge **SYS\_IDX\_46**. No es tracta de modificar aquest, sinó crear-ne un nou.

[« Anterior](322_restricci_de_clau_principal.md) | [Següent »](324_restricci_de_valor_no_nul.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 323_restricci_dunicitat.002.png
[ref2]: 323_restricci_dunicitat.003.png
[ref3]: 323_restricci_dunicitat.004.png
