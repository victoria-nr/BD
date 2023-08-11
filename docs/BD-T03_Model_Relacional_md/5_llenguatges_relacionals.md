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

[« Anterior](410_exemple.md) | [Següent »](6_exercicis.md)
# <a name="main"></a>**5. Llenguatges relacionals**


Fins el moment hem dissenyat una B.D. Relacional. Però si volem la B.D. és per consultar-la, treure la informació que ens interessa, manipular-la. Ens farà falta, per tant, un llenguatge de manipulació de la B.D. (**DML**). Aquestos llenguatges poden estar basats en l'Àlgebra Relacional o en el Càlcul Relacional.

- Per mig de l'**ÀLGEBRA RELACIONAL** farem operacions sobre les taules, combinant-les, seleccionant el que ens importa, ..., en definitiva manipulant-les. El resultat serà una nova taula, que serà el resultat final o servirà per a fer una altra operació. Les operacions poden ser **projecció** (agafar algunes columnes d'una taula), **selecció** (seleccionar algunes files d'una taula, les que acompleixen una determinada condició), **unió**, **intersecció**, **producte cartesià**, **reunió** ...

El llenguatge **SQL**, que és l'estàndard de fet i que veurem en el tema 6, està basat en l'Àlgebra relacional. Les sentències són de la forma:

SELECT dni, nom, sou 
FROM EMPLEAT
WHERE sou > 2000

on estem projectant sobre els camps dni, nom i sou, i seleccionant les files que acompleixen la condició del final



Anem a comentar dues de les operacions esmentades abans. El **producte cartesià** de dues taules consisteix en combinar cadascuna de les files d'una taula amb cadascuna de les files de l'altra. Així, el producte cartesià de **Empleat** i **Departament** seria:

SELECT dni, nom, nom\_d 
FROM EMPLEAT , DEPARTAMENT



Però aquest operació no sembla tenir molt de sentit en aquest cas ¿per a què volem combinar un empleat amb tots els departaments de l'empresa? Sembla molt més lògic combinar cada empleat únicament amb el departament al qual pertany.

La **reunió** de dues taules consisteix en fer un producte cartesià i després seleccionar les files que tenen el mateix valor en dos camps determinats (un de cada taula).

SELECT dni, nom, nom\_d 
FROM EMPLEAT , DEPARTAMENT 
WHERE EMPLEAT.departament = DEPARTAMENT.num\_d

És a dir, del producte cartesià seleccionem només les files en les quals coincideixen els camp departament i num\_d, combinant cada empleat amb el seu departament.



- En el **CÀLCUL RELACIONAL**, es defineixen variables de tipus **taula**, s'utilitzen operadors entre les variables, i també uns quantificadors (***per a tot*** i ***existeix***). Va de forma paral·lela a l'àlgebra de manera que es poden obtenir les mateixes coses amb l'Àlgebra i amb el Càlcul.

El **QBE** (Query By Example) es basa en el càlcul relacional, i la seua particularitat és la senzillesa de fer consultes per als no experts. Per mig d'una plantilla podrem col·locar els atributs que volem visualitzar, l'ordre, els criteris de selecció, etc. És el que utilitzen tant **Access** com **Base**  per a fer les consultes amb l'assistent.

![](5_llenguatges_relacionals.002.png)

[« Anterior](410_exemple.md) | [Següent »](6_exercicis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
