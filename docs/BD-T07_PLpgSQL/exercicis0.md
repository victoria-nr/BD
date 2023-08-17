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

[« Anterior](6_utilitzaci_de_cursors.md) | [Següent »](7_missatges_i_excepcions.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercicis**
7\.7.- Fes una funció anomenada **POBLACIONS\_ALTES** que accepte 2 paràmetres, el primer de tipus text que serà una comarca, i el segon numèric que serà una altura. Ha de traure les poblacions de la comarca del primer paràmetre que són més altes que el segon paràmetre. Mostrarem el nom de la població i l'altura. Aquest podria ser el resultat en executar-se:

![ref2]

7\.8.- Fes una funció anomenada **COMARQUES\_NUMPOBLES** sense paràmetres que traga per pantalla les comarques ordenades alfabèticament amb el número de pobles de cadascuna

![ref3]

7\.9.- Fes una funció anomenada **COMARQUES\_NUMPOBLES\_NUMINSTITUTS** sense paràmetres que traga per pantalla les comarques ordenades alfabèticament amb el número de pobles de cadascuna i el número d'instituts. En la consulta tindrem dos dificultats:

- Hem d'agafar totes les poblacions, fins i tot les que no tenen institut
- Com que hem d'accedir als instituts, per a comptar els pobles haurem de comptar els pobles **distints**, i així si un poble té més d'un institut, no comptar-lo més d'una vegada

![ref4]

7\.10.- Fes una funció anomenada **NUM\_HABITANTS\_COMARCA** que accepte un paràmetre de tipus text, i torne el número d'habitants d'eixa comarca

![ref5]

7\.11.- Fer la funció **COMARQUES\_NUMHABITANTS** sense paràmetres per a traure per pantalla totes les comarques i el número d'habitants. En la consulta has d'utilitzar obligatòriament la funció anterior

![ref6]

[« Anterior](6_utilitzaci_de_cursors.md) | [Següent »](7_missatges_i_excepcions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis0.002.png
[ref2]: exercicis0.003.png
[ref3]: exercicis0.004.png
[ref4]: exercicis0.005.png
[ref5]: exercicis0.006.png
[ref6]: exercicis0.007.png
