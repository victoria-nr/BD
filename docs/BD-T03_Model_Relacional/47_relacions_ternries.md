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

[« Anterior](46_resum_dependncies.md) | [Següent »](48_especialitzacions.md)
# <a name="main"></a>**4.7 Relacions ternàries**
En una relació ternària o superior construirem una nova taula, on inclourem com a claus externes les claus primàries de totes les entitats, i a més els atributs de la relació.

Habitualment, la clau principal de la nova taula serà la combinació de totes les claus principals de les entitats. Ocasionalment, si alguna entitat participa amb cardinalitat 1, la clau principal d'aquesta entitat no entraria a formar part de la clau principal de la nova taula.

Igual que en el cas de les relacions M:N, ens haurem de preguntar si és suficient amb la clau primària generada o si s'haurà d'incloure algun altre camp.

En l'exemple que vam posar de relació ternària, suposant els atributs de la relació la data de compra i la quantitat:

![ref1]

![ref2]

On hem posat totes les claus externes formant part de la clau principal, ja que totes entren amb cardinalitat N. Però no teníem prou amb aquesta clau principal, ja que el mateix departament pot comprar el mateix article al mateix proveïdor més d'una vegada. Com no teníem prou, hem posat un altre camp.

Seria moment, segurament, de substituir la clau principal que està formada per 4 camps, ja que en són massa.

Posaríem una altra clau principal, però les claus externes continuarien sent-ho, i a més serien no nules:

![ref3]

[« Anterior](46_resum_dependncies.md) | [Següent »](48_especialitzacions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 47_relacions_ternries.002.png
[ref2]: 47_relacions_ternries.003.png
[ref3]: 47_relacions_ternries.004.png
