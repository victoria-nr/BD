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

[« Anterior](1_introducci.md) | [Següent »](3_les_entitats_del_model_er.md)
# <a name="main"></a>**2. Exemple**
Anem a presentar un exemple sobre el qual ens basarem durant tot el tema. Es tracta d'una companyia, i el resultat de l'anàlisi de requeriments és el següent:

|<p>1. La companyia està organitzada en departaments. Cadascun té nom únic, número únic i un empleat que el dirigeix. Ens interessa la data en la qual va començar a dirigir-lo.</p><p>2. Cada departament controla una sèrie de projectes. Cadascun d'aquestos projectes té nom i número únics, i estarà coordinat per un únic departament.</p><p>3. De cada empleat ens interessa el nom (format per dos cognoms i nom de pila), DNI, adreça, telèfon, sou i data de naixement. Tot empleat està assignat a un departament, i moltes vegades tindrà un supervisor. Pot treballar en més d'un projecte (no necessàriament controlats pel mateix departament) i treballarà un determinat número d'hores a la setmana en cada projecte. En un projecte sempre treballarà, com a mínim, un empleat.</p><p>4. Volem saber també els familiars de cada empleat, per administrar els termes d'una assegurança. Volem saber el nom, data de naixement i parentesc amb l'empleat.</p>|
| :- |



[« Anterior](1_introducci.md) | [Següent »](3_les_entitats_del_model_er.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
