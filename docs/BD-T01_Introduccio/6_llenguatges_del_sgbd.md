# **6.Llenguatges del  SGBD**
Tant per a la construcció dels distints esquemes (administradors) com per a la posterior utilització per a introduir, modificar, eliminar i consultar dades (tots els usuaris) se li hauran de donar ordres al SGBD. Per tant el SGBD ha de proporcionar uns llenguatges als usuaris per a poder realitzar aquestes accions. Dos seran els grups de llenguatges: 

- Llenguatges de definició. Serviran per a construir els distints esquemes. Podrem distingir:

\- **Llenguatge de definició de dades** (***DDL**: data definition language*). Serviran per a construir l'esquema lògic. 

\- **Llenguatge de definició d'emmagatzematge** (***SDL**: storage definition language*), per a l'esquema físic. 

\- **Llenguatge de definició de vistes** (***VDL**: view definition language*), per a les vistes 

En la pràctica a tots aquestos (que com es comentarà més avant solen anar junts) se'ls anomena ***DDL***



- **Llenguatges de manipulació de dades** (***DML**: data manipulation language*). Serviran per a manipular les dades, és a dir fer consultes, insercions, modificacions i eliminacions.

En els SGBD actuals no s'acostuma a separar els llenguatges, sinó que s'utilitza un ampli llenguatge que combina tots els aspectes i permet fer-ho tot. Així per exemple, el llenguatge més utilitzat, el SQL, compta amb característiques de DML (SELECT), i de DDL en tots els nivells (CREATE TABLE esquema lògic, CREATE INDEX esquema físic, CREATE VIEW esquema extern). 

Hi ha dues maneres d'aplicar les sentències dels llenguatges. 

- De forma interactiva: s'escriu una sentència, s'executa, després una altra, ... Obtenen conjunts de resultats, per això s'anomenen **de conjunt en conjunt**.

- Immergits en un altre llenguatge de propòsit general, anomenat llenguatge ***amfitrió***, on entre els procediment s'inclouen les sentències del DML, anomenat llenguatge ***hoste*** o ***subllenguatge***. Normalment s'obtenen registres individuals de la B.D., per la qual cosa s'hauran d'utilitzar bucles per fer tota una consulta. Per això s'anomenen **de registre a registre**.

[« Anterior](5_arquitectura_a_3_nivells.md) | [Següent »](7_classificacions_dels_sgbd.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
