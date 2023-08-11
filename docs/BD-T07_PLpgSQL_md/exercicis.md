Bases de Dades

- [Tema 7: Programació en PostgreSQL](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [0. Nota inicial](0_nota_inicial.md)
- [1. Introducció](1_introducci.md)
- [2. PL/pgSQL](2_plpgsql.md)
- [3. Declaració de variables](3_declaraci_de_variables.md)
- [4. Instruccions](4_instruccions.md)
- [5. Funcions](5_funcions.md) 
  - [Exercicis](exercicis.md)
- [6. Utilització de cursors](6_utilitzaci_de_cursors.md) 
  - [Exercicis](exercicis0.md)
- [7. Missatges i excepcions](7_missatges_i_excepcions.md)
- [8. Triggers](8_triggers.md) 
  - [Exercicis](exercicis1.md)
- [9. Creació d'altres objectes basats en funcions](9_creaci_daltres_objectes_basats_en_funcions.md) 
  - [9.1 Operadors](91_operadors.md) 
    - [Exercicis](exercicis2.md)
  - [9.2 Operadors de classe](92_operadors_de_classe.md)
  - [9.3 Funcions d'agregat](93_funcions_dagregat.md) 
    - [Exercicis](exercicis3.md)
- [Exercicis de tot el tema](exercicis_de_tot_el_tema.md)

[« Anterior](5_funcions.md) | [Següent »](6_utilitzaci_de_cursors.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercicis**
En la Base de Dades **geo\_grup\_9999x**:

7\.1.- Crea una funció anomenada **DEU\_Q**, que traga els **números del 1 al 10** i els seus **quadrats**. (Utilitza **RAISE NOTICE**).

7\.2.- Fes una altra funció, **IMP**, que traga per pantalla els números **imparells** del 1 al 50. (Utilitza **RAISE NOTICE**).

7\.3.- Fes una funció anomenada **TAULA\_MULT**, per a que traga la taula de multiplicar del **paràmetre** que se li ha de passar. (Utilitza **RAISE NOTICE**). Aquest podria ser el seu aspecte, en executar-la:

![ref2]



7\.4.- Fes una funció, anomenada **MAX2**, que tinga dos paràmetres **numèrics** i que **torne el màxim** entre aquestos dos. (Ara ja **no** s'ha d'utilitzar **RAISE NOTICE**). Podeu comprovar el seu funcionament fent per exemple **SELECT MAX(5,7);   SELECT MAX(15,7)**. Sempre ha de mostrar el màxim dels dos.

7\.5.- Utilitza l'anterior per a crear **MAX3**. Has d'utilitzar obligatòriament la funció **MAX2**

7\.6.- (**Voluntari**) Fes la funció **LAT\_A\_TEXT**, tenint en compte que ha de quedar com en la taula **POBLACIONS**. Segurament la dificultat més gran serà aconseguir que apareguen les cometes després dels minuts i dels segons.

[« Anterior](5_funcions.md) | [Següent »](6_utilitzaci_de_cursors.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis.002.png
[ref2]: exercicis.003.png
