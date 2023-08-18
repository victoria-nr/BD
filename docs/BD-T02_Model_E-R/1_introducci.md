Bases de Dades

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
