Bases de Dades

- [Tema 2: MODEL ENTITAT-RELACIÓ](index.md)
- [Objectius i coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. Exemple](2_exemple.md)
- [3. Les Entitats del Model E/R](3_les_entitats_del_model_er.md) 
  - [3.1 Entitats](31_entitats.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple.md)
  - [3.2 Atributs](32_atributs.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple0.md)
  - [3.3 Dominis](33_dominis.md)
- [Exercicis](exercicis.md)
- [4. Les Relacions del Model E/R](4_les_relacions_del_model_er.md) 
  - [4.1 Relació](41_relaci.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple1.md)
  - [4.2 Atributs de Relació](42_atributs_de_relaci.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple2.md)
  - [4.3 Tipus de Relació o Cardinalitat](43_tipus_de_relaci_o_cardinalitat.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple3.md)
- [Exercicis](exercicis0.md)
- [5. Relacions de grau major que dos](5_relacions_de_grau_major_que_dos.md)
- [6. Model E/R Estès](6_model_er_ests.md) 
  - [6.1 Cardinalitat màxima i mínima. Participació total.](61_cardinalitat_mxima_i_mnima_participaci_total.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple4.md)
  - [6.2 Entitats dèbils](62_entitats_dbils.md)
  - [6.3 Generalització i herència](63_generalitzaci_i_herncia.md) 
    - [Aplicació a l'exemple](aplicaci_a_lexemple5.md)
- [7. Restriccions externes](7_restriccions_externes.md)
- [Exercicis](exercicis1.md)
- [Informació addicional](informaci_addicional.md)
- [Auto-avaluació](autoavaluaci.md)

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_exemple.md)
# <a name="main"></a>**1. Introducció**


El **Model Entitat-Relació** (**M E/R**) és un model d'alt nivell, que ens permetrà representar el món que volem amb un llenguatge, una estructura més propera a nosaltres. L'utilitzarem dins de tot el procés de creació de la Base de Dades, que consistirà en: 

- A partir de la realitat, estudiar-la (investigant, entrevistant els usuaris, ...) i fer l'**Anàlisi de Requeriments**, és a dir, què es vol. El resultat serà un conjunt de requeriments redactats de forma concisa. 

- A partir de l'Anàlisi de Requeriments, dissenyar l'Esquema Conceptual de la Base de Dades amb un model d'alt nivell (el **Model E/R**). 

- Traduir l'esquema conceptual, és a dir el diagrama E/R, al Model Relacional, obtenint l'Esquema Lògic.

- Implementar l'esquema lògic en un SGBD comercial. Afegir les coses necessàries (índex, retocar camps, ...) per a completar l'esquema físic, així com les vistes per a tots els usuaris (esquema extern). 


Un esquema de tot el procés seria el següent: 

![](1_introducci.002.png)

En realitat, en sistemes grans, no podem separar l'anàlisi de les dades de l'anàlisi dels processos a fer amb les dades. Aleshores, paral·lel al disseny conceptual, és a dir, després de l'anàlisi de requeriments aniria l'Anàlisi Funcional (línia discontínua), encarregat de veure quins processos generals són necessaris en el sistema. Nosaltres no filarem tan prim. 

En el Model E/R estudiarem les entitats o objectes del nostre univers, la nostra realitat, i les relacions que hi haurà entre les distintes entitats. 

El Model E/R el va proposar Peter P. Chen en 1976. Posteriorment molts autors van aportar més coses, creant l'anomenat Model E/R Estès (M EE/R), encara que en realitat hi ha tota una gamma de models estesos. 

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](2_exemple.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
