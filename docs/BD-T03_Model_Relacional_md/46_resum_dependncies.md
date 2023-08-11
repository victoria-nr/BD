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

[« Anterior](45_entitats_dbils.md) | [Següent »](47_relacions_ternries.md)
# <a name="main"></a>**4.6 Resum dependències**




Anem a fer un quadre resum amb distints graus de dependència entre dues relacions i com es traduiria al Model Relacional: 

![ref1]

Per una altra banda, si ens trobem una entitat dèbil que depèn en identificació a través d'una relació 1:1, és suficient amb la clau principal de A com a clau principal de B 

![ref2]







Una altra qüestió que pot dur a confusió és el cas de les claus externes formades per 2 camps. Ens basarem en l'exemple de sempre, en la taula FAMILIAR, ja que té una clau principal formada per 2 camps. Suposem que hi ha en el Model Entitat-Relació una taula que depèn d'ella, com podria ser comunicacions que se li han fet (cartes). Les entitats i la relació entre elles podria ser aquesta: 

![ref3]

Com que la relació és de tipus 1:N la traduirem per una clau externa en CARTES. I quina serà la clau externa? Com que la taula FAMILIAR té una clau principal formada per 2 camps, haurem de posar una clau externa formada per 2 camps. Alerta! no seran 2 claus externes, sinó una clau externa formada per 2 camps. Com sempre, representarem la clau externa amb un doble subratllat, que ara agafarà als 2 camps. 

![ref4]

[« Anterior](45_entitats_dbils.md) | [Següent »](47_relacions_ternries.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 46_resum_dependncies.002.png
[ref2]: 46_resum_dependncies.003.png
[ref3]: 46_resum_dependncies.004.png
[ref4]: 46_resum_dependncies.005.png
