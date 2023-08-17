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

[« Anterior](8_triggers.md) | [Següent »](9_creaci_daltres_objectes_basats_en_funcions.md)
# <a name="main"></a>**Exercicis**
![](exercicis1.002.png)
## **Exercicis**
En la Base de Dades **geo\_grup\_9999x**:

7\.12.- Crear un trigger anomenat **TR\_ALT\_POS** que controle que l'altura d'una nova població siga estrictament positiva. La funció en la qual es basa es pot anomenar **ALT\_POS**. 

7\.13.- Modificar l'anterior per a que ho controle també quan es tracta d'una modificació.

7\.14.- Crear un trigger anomenat **TR\_EXT\_0\_1000** que controle que l'extensió d'un municipi (població) estiga obligatòriament entre 0 i 1000, i ha de ser sempre, tant si s'insereix una nova població com si es modifica. Però en aquesta ocasió, en compte de traure un error, el que farem serà modificar aquest valor: si és major que 1000, li donarem el valor 1000, i si és negatiu li posarem 0. Ho aconseguirem modificant NEW.extensio, i com la funció del trigger torna sempre NEW, doncs agafarà el nou valor. Anomeneu a la funció **EXT\_0\_1000**. 

7\.15.- **VOLUNTARI**. En la taula POBLACIONS3 tenim controlat que la latitud introduïda siga correcta per mig del tipus lat, però no en la taula POBLACIONS, on és de tipus VARCHAR(50) i per tant es podria introduir una latitud incorrecta molt fàcilment. Crea un trigger que controle que quan s'introdueix o es modifica la **latitud** de **POBLACIONS** siga correcta. Per a això

- Els caràcters 1 i 2 han de ser els **graus**, que han d'estar entre 00 i 90
- El caràcter 3 ha de ser **º**
- Els caràcters 4 i 5 formen els **minuts**, i han d'estar entre 00 i 59
- El caràcter 6 ha de ser **'**
- Els caràcters 7 i 8 formen els **segons**, i han d'estar entre 00 i 59
- El caràcter 9 ha de ser **"**
- El caràcter 10 ha de ser **N** o **S**
- Si no s'acompleix alguna de les restriccions anteriors, ha d'eixir un error dient que la latitud ha d'estar entre 00º00'00"N i 90º00'00"N , o entre 00º00'00"S i 90º00'00"S
 

[« Anterior](8_triggers.md) | [Següent »](9_creaci_daltres_objectes_basats_en_funcions.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
