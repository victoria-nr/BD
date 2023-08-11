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

[« Anterior](3_restriccions.md) | [Següent »](32_restriccions_dusuari.md)
# <a name="main"></a>**3.1 Restriccions inherents**


Com hem dit són les que imposa el propi model. Algunes són característiques que han d'acomplir les relacions. Per tant no qualsevol taula matemàtica és una relació. Podem considerar les següents: 

- **Valors atòmics**: cada valor de la taula, és a dir, qualsevol valor de qualsevol atribut de qualsevol tupla ha de ser simple, no divisible. Per tant no valen atributs compostos o repetitius.

Així, si considerem **Nom** en la relació **Empleat** com a nom de pila més cognoms, no serà divisible (no podré agafar posteriorment el nom de pila per una banda i els cognoms per una altra; si ho volguera fer, s'haurien de definir els atributs simples **Cognom1**, **Cognom2** i **Nom**). 

Tampoc valen valors repetitius, per exemple un vector de 12 entrades. Queden per tant descartats els atributs ***multivaluats***. 

- **Tuples distintes**: no poden haver dues tuples iguals. Això és una diferència respecte a les taules matemàtiques on sí que es poden duplicar files. 

- **L'ordre de les tuples no és significatiu**. 

- **L'ordre dels atributs no és significatiu**. 

[« Anterior](3_restriccions.md) | [Següent »](32_restriccions_dusuari.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
