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

[« Anterior](exercicis3.md)
# <a name="main"></a>**Exercicis de tot el tema**
![ref1]
## **Exercicis**
En la Base de Dades **geo\_grup\_9999x**:

7\.1.- Crea una funció anomenada **DEU\_Q**, que traga els **números del 1 al 10** i els seus **quadrats**. (Utilitza **RAISE NOTICE**).

7\.2.- Fes una altra funció, **IMP**, que traga per pantalla els números **imparells** del 1 al 50. (Utilitza **RAISE NOTICE**).

7\.3.- Fes una funció anomenada **TAULA\_MULT**, per a que traga la taula de multiplicar del **paràmetre** que se li ha de passar. (Utilitza **RAISE NOTICE**). Aquest podria ser el seu aspecte, en executar-la:

![ref2]

7\.4.- Fes una funció, anomenada **MAX2**, que tinga dos paràmetres **numèrics** i que **torne el màxim** entre aquestos dos. (Ara ja **no** s'ha d'utilitzar **RAISE NOTICE**).

7\.5.- Utilitza l'anterior per a crear **MAX3**. Has d'utilitzar obligatòriament la funció **MAX2**

7\.6.- (**Voluntari**) Fes la funció **LAT\_A\_TEXT**, tenint en compte que ha de quedar com en la taula **POBLACIONS**. Segurament la dificultat més gran serà aconseguir que apareguen les cometes després dels minuts i dels segons.

7\.7.- Fes una funció anomeneda **POBLACIONS\_ALTES** que accepte 2 paràmetres, el primer de tipus text que serà una comarca, i el segon numèric que serà una altura. Ha de traure les poblacions de la comarca del primer paràmetre que són més altes que el segon paràmetre. Mostrarem el nom de la població i l'altura. Aquest podria ser el resultat en executar-se:

![ref3]

7\.8.- Fes una funció anomenada **COMARQUES\_NUMPOBLES** sense paràmetres que traga per pantalla les comarques ordenades alfabèticament amb el número de pobles de cadascuna

![ref4]

7\.9.- Fes una funció anomenada **COMARQUES\_NUMPOBLES\_NUMINSTITUTS** sense paràmetres que traga per pantalla les comarques ordenades alfabèticament amb el número de pobles de cadascuna i el número d'instituts. En la consulta tindrem dos dificultats:

- Hem d'agafar totes les poblacions, fins i tot les que no tenen institut
- Com que hem d'accedir als instituts, per a comptar els pobles haurem de comptar els pobles distints, i així si un poble té més d'un institut, no comptar-lo més d'una vegada

![ref5]

7\.10.- Fes una funció anomenada **NUM\_HABITANTS\_COMARCA** que accepte un paràmetre de tipus text, i torne el número d'habitants d'eixa comarca

![ref6]

7\.11.- Fer la funció **COMARQUES\_NUMHABITANTS** sense paràmetres per a traure per pantalla totes les comarques i el número d'habitants. En la consulta has d'utilitzar obligatòriament la funció anterior

![ref7]

7\.12.- Crear un trigger anomenat **TR\_ALT\_POS** que controle que l'altura d'una nova població siga estrictament positiva. La funció en la qual es basa es pot anomenar **ALT\_POS**.

7\.13.- Modificar l'anterior per a que ho controle també quan es tracta d'una modificació.

7\.14.- Crear un trigger anomenat **TR\_EXT\_0\_1000** que controle que l'extensió d'un municipi (població) estiga obligatòriament entre 0 i 1000, i ha de ser sempre, tant si s'insereix una nova població com si es modifica. Però en aquesta ocasió, en compte de traure un error, el que farem serà modificar aquest valor: si és major que 1000, li donarem el valor 1000, i si és negatiu li posarem 0. Ho aconseguirem modificant **NEW.extensio**, i com la funció del trigger torna sempre NEW, doncs agafarà el nou valor. Anomeneu a la funció **EXT\_0\_1000**. 

7\.15.- **VOLUNTARI**. En la taula POBLACIONS3 tenim controlat que la latitud introduïda siga correcta per mig del tipus lat, però no en la taula POBLACIONS, on és de tipus VARCHAR(50) i per tant es podria introduir una latitud incorrecta molt fàcilment. Crea un trigger que controle que quan s'introdueix o es modifica la **latitud** de **POBLACIONS** siga correcta. Per a això

- Els caràcter 1 i 2 han de ser els **graus**, que han d'estar entre 00 i 90
- El caràcter 3 ha de ser **º**
- Els caràcters 4 i 5 formen els **minuts**, i han d'estar entre 00 i 59
- El caràcter 6 ha de ser **'**
- Els caràcters 7 i 8 formen els **segons**, i han d'estar entre 00 i 59
- El caràcter 9 ha de ser **"**
- El caràcter 10 ha de ser **N** o **S**
- Si no s'acompleix alguna de les restriccions anteriors, ha d'eixir un error dient que la latitud ha d'estar entre 00º00'00"N i 90º00'00"N , o entre 00º00'00"S i 90º00'00"S

7\.16.- Crear els dos **operadors de comparació** que quedaven per al tipus **lat**: **<** i **<=**

7\.17.- Crear la funció d'agregat **MIN** per al tipus de dades **lat**.

7\.18.- **VOLUNTARI**. Fes una funció en PL/pgSQL anomenada **DENSITAT\_CENTRES** que donat el nom d'una comarca ens torne la quantitat de centres que té per unitat de superfície.

![ref8]

7\.19.- **VOLUNTARI**. Fes una funció anomenada **introduir\_institut(varchar,varchar,varchar,varchar,numeric,numeric)**, que accepte els paràmetres indicats, un per cada camp de la taula INSTITUTS, que comprove:

- Que el primer paràmetre, el codi de l’institut, tinga exactament 8 caràcters i que comence per 03, 12 o 46 (els codis de província)
- Que el codi postal estiga entre 3001 i 3999, 12001 i 12999 o 46001 i 46999
- Observa que el cod\_m no caldrà comprovar-lo, ja que és clau externa i saltaria l’error si no és un codi de municipi existent

En cas que tot siga correcte, s’ha d’introduir el nou institut. En cas contrari ha de saltar un error

7\.20.- **VOLUNTARI**. Fes un trigger per a portar una auditoria de la taula **INSTITUTS** per a controlar totes les modificacions que es fan en la taula INSTITUTS. Per a això per cada actualització feta, introduirem una fila en la taula nova anomenada **AUDIT\_INSTITUT** (creant-la prèviament si no existeix) amb la següent informació:

- **num\_a**: és la clau principal de la taula, que serà un autonumèric (SERIAL)
- **operacio**: contindrà el tipus d’operació d’actualització realitzada en la taula INSTITUTS, que podrà ser: INSERT, DELETE o UPDATE
- **codi\_institut**: codi del institut afectat per l’operació d’actualització
- **usuari**: usuari que ha realitzat l’operació d’actualització; es pot obtenir amb **current\_user**;
  podríem pensar que sempre serà el mateix usuari qui fa l’operació, però en realitat ho pot fer tot usuari que tinga permís d’accés a la Base de Dades. En la imatge es pot observar com l’usuari **postgres** també ha fet una operació d’actualització
- **data\_op**: data-hora (timestamp) de l’actualització; es pot obtenir amb la funció **now()**

En la imatge s’observa com s’han fet 3 actualitzacions des del moment de creació del trigger, l’ultima d’elles realitzada per l’usuari **postgres**. Evidentment, la manera de comprovar-lo vosaltres és fer operacions d'actualització i el resultat ha de ser obligatòriament deferent:

![ref9]

[« Anterior](exercicis3.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis_de_tot_el_tema.002.png
[ref2]: exercicis_de_tot_el_tema.003.png
[ref3]: exercicis_de_tot_el_tema.004.png
[ref4]: exercicis_de_tot_el_tema.005.png
[ref5]: exercicis_de_tot_el_tema.006.png
[ref6]: exercicis_de_tot_el_tema.007.png
[ref7]: exercicis_de_tot_el_tema.008.png
[ref8]: exercicis_de_tot_el_tema.009.png
[ref9]: exercicis_de_tot_el_tema.010.png
