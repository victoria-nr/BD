# **3.Característiques desitjables d'un SGBD**
Ja hem vist algunes característiques que han de tenir els SGBD. Anem a completar aquest llista.

- **Control de redundància**. Ja hem comentat que potser siga convenient en algunes ocasions un poc de redundància. Però en cas que hi haja, aquesta ha d'estar controlada. És a dir, el SGBD hauria de proporcionar mecanismes per a controlar les dades que estan duplicades, i que quan una informació s'actualitze en un lloc, automàticament s'actualitze en els altres.
- **Restricció d'accessos no autoritzats**. Quan molts usuaris utilitzen la B.D., és normal que no tots tinguen autorització per a accedir a tota la informació. Pot haver informació confidencial a la qual pocs usuaris tenen accés, i pot haver informació a la qual un usuari pot tenir accés però que no pot modificar. El SGBD ha de tenir, per tant, un subsistema de seguretat i autorització per a crear usuaris (que s'identifiquen amb una contrasenya) i donar distints permisos d'accés a cadascun.
- **Subministrament de múltiples interfícies per als usuaris**. Com que hi ha molts tipus d'usuaris, amb nivells de coneixements tècnics distints, el SGBD ha d'oferir diferents interfícies: llenguatges de consulta per a usuaris esporàdics, llenguatges de definició i control per a administradors, formularis per a usuaris habituals, ...
- **Compliment de restriccions**. Hi haurà restriccions que han de complir les dades. Per exemple la nota d'un alumne ha d'estar entre 0 i 10; la data de naixement no pot ser posterior a l'actual; el curs on està matriculat un alumne ha de ser un curs existent; un alumne que estiga de baixa ha de tenir contingut en la data de baixa, o no se li poden posar notes; ... Algunes d'aquestes restriccions les suportarà directament el SGBD. Altres requeriran verificació per mig de programa quan s'introduesca o es modifique la dada.
- **Recolzament i recuperació**. Tot SGBD ha de comptar amb recursos per a recuperar-se d'errades del hardware o del software i deixar les dades com estaven abans de la fallida.

[« Anterior](2_concepte_de_base_de_dades.md) | [Següent »](4_models_de_dades.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
