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

[« Anterior](exercicis0.md) | [Següent »](6_model_er_ests.md)
# <a name="main"></a>**5. Relacions de grau major que dos**


Anem a estudiar una miqueta més el cas de les relacions ternàries. Donada la seua complexitat podríem, i de fet així es fa de vegades, descompondre-la en tres relacions binàries 



![ref1]



Així pot haver una ocurrència que Comptabilitat adquireix una calculadora, una altra que Comptabilitat compra a Distribucions Garcia, S.L., i una altra que Distribucions Garcia, S.L. subministra calculadores. 

Però això no té per què voler dir que la calculadora comprada per Comptabilitat, l'haja comprada a Distribucions Garcia, S.L. Pot haver-la comprada a un altre proveïdor, i el que li compra a Garcia són bolígrafs (encara que Garcia també en puga vendre de calculadores). 

En canvi en una relació ternària es diu qui compra, què compra i a qui compra. Per tant una relació ternària proporciona més informació que 3 binàries. 



![ref2]



La cardinalitat es calcula fixant-ne 2 i veient quantes ocurrències entren en la tercera. Així, un determinat departament pot comprar un determinat article a més d'un proveïdor (N). Un article d'un proveïdor el pot comprar més d'un departament (N). I un departament pot comprar a un proveïdor més d'un article. No té perquè ser sempre N:N:N (en aquest cas de les ternàries no utilitzarem ja la M, només la N). Per exemple suposem que un departament sempre compra un article al mateix proveïdor; aleshores en Proveïdor tindríem 1. 



![ref3]





Algunes ferramentes de disseny de B.D. només permeten relacions binàries. Aleshores s'hauria de fer un truc per a representar la relació ternària, construint una entitat nova, dèbil, que depenga en identificació de les altres 3. Veurem les entitats dèbils en el següent punt. 



![ref4]** 

[« Anterior](exercicis0.md) | [Següent »](6_model_er_ests.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 5_relacions_de_grau_major_que_dos.002.png
[ref2]: 5_relacions_de_grau_major_que_dos.003.png
[ref3]: 5_relacions_de_grau_major_que_dos.004.png
[ref4]: 5_relacions_de_grau_major_que_dos.005.png
