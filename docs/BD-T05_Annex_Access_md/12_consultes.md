Bases de Dades

- [Tema 5 (annex): Access avançat](index.md)
- [Objectius](objectius.md)
- [Part I: Pràctica inicial](part_i_prctica_inicial.md) 
  - [1.1 Taules](11_taules.md)
  - [1.2 Consultes](12_consultes.md)
  - [1.3 Formularis i Informes](13_formularis_i_informes.md)
- [Part II: Macros](part_ii_macros.md) 
  - [2.1 Creació d'una Macro](21_creaci_duna_macro.md)
  - [2.2 Accions múltiples](22_accions_mltiples.md)
  - [2.3 Submacros](23_submacros.md)
  - [2.4 Condicions](24_condicions.md)
  - [2.5 Resum d'accions](25_resum_daccions.md)
  - [2.6 Resum d'esdeveniments](26_resum_desdeveniments.md)
- [Part III: Mòduls (Visual Basic)](part_iii_mduls_visual_basic.md) 
  - [3.1 Creació d'un Mòdul](31_creaci_dun_mdul.md)
  - [3.2 Tipus de dades, Constants i Variables](32_tipus_de_dades_constants_i_variables.md)
  - [3.3 Tipus especials](33_tipus_especials.md)
  - [3.4 Operadors](34_operadors.md)
  - [3.5 Funcions i Procediments](35_funcions_i_procediments.md)
  - [3.6 Sentències](36_sentncies.md)
  - [3.7 Funcions estàndard](37_funcions_estndard.md)
  - [3.8 Objectes especials: propietats i mètodes](38_objectes_especials_propietats_i_mtodes.md)
- [Part IV: Configurar l'aspecte](part_iv_configurar_laspecte.md) 
  - [4.1 Configurar la Barra d'Accés ràpid](41_configurar_la_barra_daccs_rpid.md) 
    - [Exercici 4.1](exercici_41.md)
  - [4.2 La cinta d'opcions](42_la_cinta_dopcions.md) 
    - [4.2.1 Modificació per a tot Access](421_modificaci_per_a_tot_access.md) 
      - [Exercici 4.2](exercici_42.md)
    - [4.2.2 Modificació per a la Base de Dades actual](422_modificaci_per_a_la_base_de_dades_actual.md) 
      - [Exercici 4.3 (voluntari però puntuable)](exercici_43_voluntari_per_puntuable.md)
  - [4.3 El panell de navegació](43_el_panell_de_navegaci.md)
  - [4.4 Opcions d'aplicació](44_opcions_daplicaci.md) 
    - [Exercici 4.4](exercici_44.md)
  - [4.5 El panell de control](45_el_panell_de_control.md) 
    - [Exercici 4.5](exercici_45.md)

[« Anterior](11_taules.md) | [Següent »](13_formularis_i_informes.md)
# <a name="main"></a>**1.2 Consultes**
Continueu amb les següents qüestions:

**1.8)** Construir una consulta anomenada **1-8:  Empleats - Sou en Pessetes** on tindrem el nom de l'empleat, Dni, sou en euros i sou en pessetes. (1euro = 166,386pts). Aquesta consulta ha d'anar ordenada de major sou a menor.



**1.9)** Fer una consulta, **1-9: Empleats - comencen per G**, on aparega el nom i dni d'aquells empleats que comencen per **G**.



**1.10)** Construir una consulta, **1-10: Empleats - Departaments**, amb el nom dels empleats i els noms dels departaments als quals pertanyen. Ordenat per nom d'empleat.

![ref1]

**Atenció**

És més complicada del que sembla en un principi, ja que podeu tenir un efecte no desitjat. Observeu que hi ha d'haver 7 files en total.



**1.11)** Construir una consulta anomenada **1-11: Empleats - Número de Projectes** on tindrem el nom de l'empleat, Dni i número de projectes en els quals treballa** 

![ref2]

**1.12)** Construir una consulta pareguda a l'anterior anomenada **1-12: Projecte - Total d'hores** on tindrem el nom del projecte, el número de projecte i la suma de les hores treballades en ell.** 

![ref3]

**1.13)** Construir una consulta anomenada **1-13: Familiars dels empleats amb sous mitjans d'un departament**, on tindrem número de departament, Dni, nom de l'empleat, nom del familiar, parentesc i sou de l'empleat, ordenat per nom empleat, dels empleats que tenen un sou entre 2.000 i 2.500 €. (ambdós inclosos) d'un departament introduït per teclat (serà un paràmetre). Per exemple, si quan pregunte el departament s'introdueix el **3**, el resultat seria:

![ref4]

**Nota**

Per a posar un paràmetre en una consulta per a que ens demane el valor per teclat, hem de posar entre claudàtors (**[ ]**) un nom que no siga com cap camp de les taules que entren en la consulta. D'aquesta manera, ens demanarà el valor per teclat.

**1.14)** Crear una consulta per a augmentar el sou un 5% als empleats del departament 3. Guardar aquesta consulta com: **1-14: Empleats - Augment Sou**. El resultat d'executar-la serà que a partir d'ara els 2 empleats del departament 3 tindran un sou de 2.100€ (abans el tenien de 2.000€). Ho podeu comprovar obrint la taula EMPLEAT.

**Atenció** 
Aquesta consulta només s'ha d'executar una vegada (sinó augmentaríem el sou més i més d'aquestos 2 empleats). Access només avisa que va a procedir a actualitzar un número determinat de files, però després no trau cap resultat. Clar, perquè aquesta consulta és de modificació de dades, i no de mostrar dades.



**1.15)** Construir una consulta de supervisors, on tindrem els dni i nom de **tots** els empleats, i el nombre de empleats que supervisa cadascun. Guardeu-la amb el nom **1-15: Empleats - Supervisors**.

![ref5]

**Pista**

Farà falta posar 2 vegades la taula Empleat, una per a traure el nom i dni de cada empleat, i una altra per a poder comptar els que tenen a aquest de supervisor. I mireu que han d'eixir **tots** els empleats (fins i tot els que no supervisen a ningú, que són als que ix 0) 

[« Anterior](11_taules.md) | [Següent »](13_formularis_i_informes.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 12_consultes.002.png
[ref2]: 12_consultes.003.png
[ref3]: 12_consultes.004.png
[ref4]: 12_consultes.005.png
[ref5]: 12_consultes.006.png
