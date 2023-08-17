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

[« Anterior](47_relacions_ternries.md) | [Següent »](49_restriccions_externes.md)
# <a name="main"></a>**4.8 Especialitzacions**




Aquest aspecte, com en el cas de les relacions 1:1, també té múltiples solucions. El problema de les especialitzacions és que, encara que de forma teòrica la solució siga correcta, en la pràctica suposa moltes taules i amb un cert grau de manteniment entre elles. Per tant, i aplicant el sentit comú, moltes vegades es fa una simplificació, llevant bé les subclasses, bé la superclasse, com veurem a continuació. Aquestes són les possibilitats: 

- Transformar les especialitzacions en taules amb la clau principal heretada i els atributs específics (com si substituírem l'especialització en relacions 1:1, amb les subclasses depenent en identificació de la superclasse). Estaria també bé afegir un atribut a la superclasse per a poder saber de quin tipus és. En l'exemple ens quedaria:

![ref1]

- Simplificar les subclasses. Aleshores tots els atributs d'aquestes haurien de passar a la superclasse. També s'haurien de passar totes les relacions que afecten a les subclasses, "retocant" les participacions totals (que ara ja no ho serien). Ara serà obligatori tenir el camp que distingeix el tipus (sinó, perdríem aquesta informació).

![ref2]



- Simplificar la superclasse. Aleshores tots els atributs d'aquesta passarien a cadascuna de les subclasses. També passarien les relacions a cadascuna d'aquestes, "retocant" les participacions totals.

![ref3]

[« Anterior](47_relacions_ternries.md) | [Següent »](49_restriccions_externes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 48_especialitzacions.002.png
[ref2]: 48_especialitzacions.003.png
[ref3]: 48_especialitzacions.004.png
