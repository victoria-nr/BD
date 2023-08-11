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

[« Anterior](41_entitats.md) | [Següent »](43_relacions_mn.md)
# <a name="main"></a>**4.2 Relacions 1:N**
Per cada relació 1:N entre les entitats **A** i **B**, on **A** és la que participa amb grau de cardinalitat 1, i **B** amb grau N, s'inclou un nou camp en **B** (del mateix tipus que la clau principal de **A**) que a més serà **clau externa** que apuntarà a **A**, més concretament a la clau principal de **A**. En moltes ocasions al camp nou de **B** se li posa el mateix nom que a la clau principal de **A**, però no és necessari, depén del gust de cadascú.

També s'inclouran en **B** tots els possibles atributs de la relació.

La següent animació intenta explicar-ho millor:

Si a més l'entitat que participa amb grau N ho fa de forma **total** (com en la figura de baix), la clau externa **no pot ser nula** (és a dir sempre ha de tenir un valor).

![ref1]

En l'exemple nostre:

- Per la relació **Pertany** (figura de dalt) inclourem l'atribut **departament** a **Empleat**, que a més haurà de ser no nul.
- Per la relació **Controla** inclourem l'atribut **departament** a **Projecte** (no nul).
- Per la relació **Supervisa** inclourem l'atribut **supervisor** a **Empleat** (és reflexiva), però aquest sí que pot ser nul. Encara que semble estrany, un camp pot ser clau externa que apunta a la clau principal de la mateixa taula.
- Per la relació **Té** entre empleat i familiar, inclourem en **FAMILIAR** l'atribut **dni\_e**, però com que Familiar és dèbil la veurem millor un poc més endavant.

![ref2]

[« Anterior](41_entitats.md) | [Següent »](43_relacions_mn.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 42_relacions_1n.002.png
[ref2]: 42_relacions_1n.003.png
