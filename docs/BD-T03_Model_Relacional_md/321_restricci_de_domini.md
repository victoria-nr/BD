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

[« Anterior](32_restriccions_dusuari.md) | [Següent »](322_restricci_de_clau_principal.md)
# <a name="main"></a>**3.2.1 Restricció de domini**




El valor d'un atribut ha de ser un valor atòmic del domini. Definint clarament el domini ens assegurem (dins del possible) que l'atribut no puga agafar valors incorrectes.

Per una banda, el domini serà d'un tipus determinat, triat d'una gamma prou extensa: enter curt, enter, enter llarg, real, doble precisió, caràcter, cadena de caràcters (text), data, hora, ...

Així, per exemple, definint el *Sou* com un número real impedirem que per error puga agafar el valor 2.**R**00'00, o que la *data de naixement*, amb domini de tipus data, siga 15-**14**-1958 o **31**-**2**-1958.

També es podran definir dominis que estiguen en un determinat interval (nota d'un examen: 0-10) o d'un tipus enumerat (nota d'avaluació: MD, IN, SUF, BE, NOT, EXC).

Es poden definir regles de verificació o validació (**CHECK**) que ens ajuden a perfilar molt bé el domini. Aquest seria un exemple d'exigir que el treballador tinga de 18 a 65 anys. La sintaxi és inventada, només per a entendre-ho, amb una hipotètica funció que trau l'any, i una altra que ens dóna la data d'avui.

CHECK ( Any(avui - data\_n) >= 18) and (Any(avui - data\_n) < 65) )



**Nota**

En **Access** la regla de validació seria:

AgregFecha("aaaa";18;[data\_n])<=Ahora() Y AgregFecha("aaaa";65;[data\_n])>=Ahora()

on es veu que la fórmula és afegir 18 anys a la data de naixement i comprovar que no supera la data d'avui; i afegir 65 anys a la data de naixement i comprovar que sí supera la data d'avui.



Per exemple, **Empleat** podria quedar:

EMPLEAT (dni:caràcter(10), nom:caràcter(30), adreca:caràcter(30), telefon:enter(9), sou:numèric(6,2), data\_n:data)

amb la regla de validació:

CHECK Sou > 0

a banda de la mencionada anteriorment.

Si utilitzem la manera de representar alternativa, ho tindríem així:

![ref1]



La següent imatge mostra com es faria en **Access** la primera regla de validació, aplicada al camp **data\_n**

![ref2]

**Nota**

En Base de LibreOffice resulta més complicada la creació de regles de validació. S'ha de fer per mig de Macros associades a formularis

[« Anterior](32_restriccions_dusuari.md) | [Següent »](322_restricci_de_clau_principal.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 321_restricci_de_domini.002.png
[ref2]: 321_restricci_de_domini.003.png
