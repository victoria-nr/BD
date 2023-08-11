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

[« Anterior](5_relacions_de_grau_major_que_dos.md) | [Següent »](61_cardinalitat_mxima_i_mnima_participaci_total.md)
# <a name="main"></a>**6. Model E/R Estès**


El que hem vist fins ara proporciona una eina per descriure la realitat molt potent. Però encara hi ha restriccions del món real que no podem representar. 

Per exemple, de l'entitat FAMILIAR no ens interessen tots els familiars del món, únicament els familiars dels empleats. És més, si un empleat deixa de treballar en l'empresa, ja no ens interessen els familiars. 

O un altre exemple, hem posat que la relació DIRIGEIX és **1:1**, i això ens podria fer pensar que les dues entitats, EMPLEAT i DEPARTAMENT, participen exactament de la mateixa manera en la relació. Però no és exactament així, ja que tot departament tindrà un empleat que el dirigeix, però no tot empleat té un departament a dirigir. 

Això fa que el Model E/R s'haja desenvolupat amb les aportacions de més autors, fins arribar al **MODEL ENTITAT-RELACIÓ ESTÈS**. 

[« Anterior](5_relacions_de_grau_major_que_dos.md) | [Següent »](61_cardinalitat_mxima_i_mnima_participaci_total.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
