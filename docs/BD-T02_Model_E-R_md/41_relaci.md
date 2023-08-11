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

[« Anterior](4_les_relacions_del_model_er.md) | [Següent »](aplicaci_a_lexemple1.md)
# <a name="main"></a>**4.1 Relació**


**RELACIÓ<a name="_ftnref1"></a>[\[1\]](#_ftn1 "_ftnref1")** és una associació o correspondència entre entitats. 

El **TIPUS DE RELACIÓ** serà l’estructura genèrica, l’associació entre dos tipus d’entitat, i englobarà les **OCURRÈNCIES DE RELACIÓ**, que relacionaran ocurrències de les entitats (Joan Peris pertany al departament de Comptabilitat, Pilar Gomis al de Vendes, ...). 

Representarem la relació per un rombe, amb el nom de la relació a l’interior. Habitualment serà un verb que descriu la relació entre les dues entitats. Unirem el rombe amb els rectangles de les entitats per mig de línies. 

Així tindrem: 

![ref1]

En una Relació poden intervenir 2 entitats (Relació Binària), 3 entitats (ternària), o fins i tot més. Aquest número serà el **GRAU** de la relació. 

Un exemple de relació ternària seria: 

![ref2]

I una ocurrència d’aquesta relació podria ser: Comptabilitat compra una calculadora a Distribucions Garcia, S.L. 

També es pot donar el cas que només intervinga una entitat. Aleshores seria reflexiva o de grau 1. Per exemple, els empleats tenen un supervisor, que també és un empleat de la companyia. 

![ref3]

Per últim, també es pot donar el cas que dues entitats tinguen entre elles més d’una relació. En el nostre exemple els empleats pertanyen als departaments. Però alguns empleats dirigeixen els departaments, i aquesta és una relació distinta de l’anterior. Per això convé posar el nom de la relació, per evitar confusions. 

![ref4]



**Nota**

Potser a mida que fem exercicis ens entre perea de posar nom a totes les relacions, sobretot perquè moltes estarà molt clar què signifiquen. Però haurem de posar sempre el nom en aquelles que puguen dur a confusió o aquelles que no està clar el seu significat. 


\-----

<a name="_ftn1"></a>[\[1\]](#_ftnref1 "_ftn1") Per a no confondre amb les Relacions del Model Relacional, alguns autors prefereixen traduir el mot anglès *Relationship* com **Interrelació** o **Vincle** en compte de **Relació**

[« Anterior](4_les_relacions_del_model_er.md) | [Següent »](aplicaci_a_lexemple1.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 41_relaci.002.png
[ref2]: 41_relaci.003.png
[ref3]: 41_relaci.004.png
[ref4]: 41_relaci.005.png
