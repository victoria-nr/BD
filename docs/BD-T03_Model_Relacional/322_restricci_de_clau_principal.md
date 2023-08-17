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

[« Anterior](321_restricci_de_domini.md) | [Següent »](323_restricci_dunicitat.md)
# <a name="main"></a>**3.2.2 Restricció de clau principal**
Permet declarar un atribut o un conjunt d'atributs com a **CLAU PRINCIPAL** o **PRIMÀRIA** (Primary Key). Aquesta clau principal servirà per a identificar unívocament cadascuna de les files.

Com a conseqüència de l'anterior, la clau principal no podrà agafar valors nuls ni repetits, ja que en cas contrari no es podria assegurar la identificació de les files.

Aquestes últimes característiques també les podran tenir altres atributs, cosa que dóna lloc als tipus de restricció que es veuen en els següents punts.

Nosaltres sempre definirem una clau principal. Si tenim claus candidates, triem una d'elles com a clau principal. Si no en tenim, ens inventem un camp que servirà de clau principal (bé un número o bé un codi alfanumèric).

No és convenient que la clau principal estiga formada per un número excessiu de camps. Podríem dir que 3 és el màxim. Si la clau candidata està formada per més de 3 camps, o bé triem una altra clau candidata, o bé ens inventem una.

En **Access** es marca la clau principal amb una figura d'una clau. En la figura es veu com fer que el camp **dni** siga la clau principal de la taula **EMPLEAT**:

![ref1]

En **LibreOffice Base** es fa de la mateixa manera:

![ref2]

[« Anterior](321_restricci_de_domini.md) | [Següent »](323_restricci_dunicitat.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 322_restricci_de_clau_principal.002.png
[ref2]: 322_restricci_de_clau_principal.003.png
