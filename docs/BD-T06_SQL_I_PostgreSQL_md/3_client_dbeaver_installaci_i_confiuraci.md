Bases de Dades

- [Tema 6: SQL - Consulta bàsica (part I)](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. DDL i DML](2_ddl_i_dml.md)
- [3. Client DBeaver: instal·lació i confiuració](3_client_dbeaver_installaci_i_confiuraci.md)
- [4. Client DBeaver: utilització](4_client_dbeaver_utilitzaci.md)
- [5. Dades dels exemples i els exercicis](5_dades_dels_exemples_i_els_exercicis.md)
- [6. Operadors](6_operadors.md)
- [7. Funcions](7_funcions.md) 
  - [7.1 Formats de les dates](71_formats_de_les_dates.md)
  - [7.2 Formats dels números](72_formats_dels_nmeros.md)
- [8. La consulta SELECT](8_la_consulta_select.md)
- [9. Consulta bàsica](9_consulta_bsica.md) 
  - [Exercicis](exercicis.md)
- [10. Àlies en les columnes](10_lies_en_les_columnes.md) 
  - [Exercicis](exercicis0.md)
- [11. La clàusula WHERE](11_la_clusula_where.md) 
  - [Exercicis](exercicis1.md)
- [12. Funcions d'agregat](12_funcions_dagregat.md) 
  - [Exercicis](exercicis2.md)
- [13. La clàusula GROUP BY](13_la_clusula_group_by.md) 
  - [Exercicis](exercicis3.md)
- [14. La clàusula HAVING](14_la_clusula_having.md) 
  - [Exercicis](exercicis4.md)
- [15. La clàusula ORDER BY](15_la_clusula_order_by.md) 
  - [Exercicis](exercicis5.md)
- [16. El predicat DISTINCT](16_el_predicat_distinct.md) 
  - [Exercicis](exercicis6.md)
- [17. La clàusula LIMIT .. OFFSET](17_la_clusula_limit__offset.md) 
  - [Exercicis](exercicis7.md)
- [18. Consulta de creació de taules](18_consulta_de_creaci_de_taules.md) 
  - [Exercicis](exercicis8.md)
- [19. Ordre amb què s'executa una sentència SQL](19_ordre_amb_qu_sexecuta_una_sentncia_sql.md)
- [Exercicis de tot el tema, amb els resultats](exercicis_de_tot_el_tema_amb_els_resultats.md)

[« Anterior](2_ddl_i_dml.md) | [Següent »](4_client_dbeaver_utilitzaci.md)
# <a name="main"></a>**3. Client DBeaver: instal·lació i confiuració**
Com ja s'ha comentat, en aquest tema utilitzarem el Sistema Gestor de Bases de Dades **PostgreSQL**. Aquest SGBD utilitza l'arquitectura **client-servidor**. Això significa que hi ha un servidor central amb el PostgreSQL instal·lat, i hi haurà molts clients que es connectaran a aquest servidor. Es pot fer des de la mateixa màquina on està instal·lat el servidor, o des d'una altra.

En el nostre cas, el servidor ja està en marxa i funcionant. Podrem accedir a ell tant des de dins de l'Institut com des de fora.

A nosaltres, per a poder connectar amb el servidor PostgreSQL ens fa falta el **client de PostgreSQL**.

Instal·larem **DBeaver**, un programa que està pegant molt fort i ens permet accedir a qualsevol Sistema Gestor de Bases de Dades molt còmodament.

En els ordinadors de l'Institut ja el tenim instal·lat. En casa us l'haureu d'instal·lar però la seua instal·lació no ofereix cap problema.

Haureu d'anar a la pàgina de DBeaver, concretament a la de Downloads: <https://dbeaver.io/download/>

Triarem la versió **Comunity Edition**, amb ella tindrem de sobres i és totalment lliure. Com veieu es pot instal·lar sense problemes en Windows, Mac i/o Linux

![ref1]

La versió Enterprise Edition també ens permetria accedir a moltíssimes Bases de Dades NoSQL. Com veieu molt interessant.

Com hem dit amb la versió Comunity Edition tindrem més que suficient.

Tant en Linux com en Windows tenim la possibilitat de baixar-nos un fitxer comprimit (zip o tar.gz respectivament) que només haurem de descomprimir i buscar l'executable. També tenim la possibilitat de baixar-nos l'instal·lador, que en Windows seria un executable i en Linux un paquet. Però la primera opció del fitxer comprimit ens anirà bé.

La versió en el moment de fer aquestos apunts és la 21.2.4

Una vegada feta la instal·lació haurem de fer la connexió amb el SGBD que en el nostre cas serà PostgreSQL. Però connectar a qualsevol altre SGBD seria exactament igual.

La primera vegada que arranquem el programa, segurament ens demanarà per fer la primera connexió. Arribarem a la mateixa finestra cada vegada que anem a fer una nova connexió.

Primera connexió a PostgreSQL: geo

Especificarem que volem connectar a PostgreSQL i a continuació donarem les dades de connexió, que són aquestes:

- Servidor (**Host**): **89.36.214.106**
- Base de Dades (**Database**): **geo**
- Usuari (**Username**): **geo**
- Contrasenya (**Password**): **geo**

En aquesta Base de Dades tindrem unes taules que ens serviran per a fer els exercicis de SQL. Comentarem la seua estructura més endavant.

Aquestes són les finestres on especificaríem l'anterior:

|![ref2]|![ref2]|
| :- | :- |

Segona connexió a PostgreSQL: factura

Per als exercicis treballarem sobre una altra Base de Dades més completa que ens done més joc a l'hora de fer les sentències SQL. La Base de Dades s'anomena factura, i s'ha de connectar amb l'usuari factura amb contrasenya factura. Comentarem la seua estructura més endavant. Aquestes són les dades de connexió:

- Servidor (**Host**): **89.36.214.106**
- Base de Dades (**Database**): **factura**
- Usuari (**Username**): **factura**
- Contrasenya (**Password**): **factura** 

` `Aquestes són les pantalles on faríem la connexió:

|![ref2]|![ref2]|
| :- | :- |

Exemple de connexió a Access: Empresa.accdb

Únicament a mode il·lustratiu anem a mostrar una altra connexió diferent a les de PostgreSQL. Com que de moment només havíem treballat amb **Access**, anem a intentar connectar amb la Base de Dades **Empresa.accdb** feta en el tema anterior. 

La connexió l'haurem de fer a **MS Access (UCanAccess)**. Després només haurem de navegar per trobar la Base de Dades **Empresa.accdb**

Ací presentem les pantalles per a fer la connexió:

|![ref3]|![ref3]|
| :- | :- |

[« Anterior](2_ddl_i_dml.md) | [Següent »](4_client_dbeaver_utilitzaci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 3_client_dbeaver_installaci_i_confiuraci.002.png
[ref2]: 3_client_dbeaver_installaci_i_confiuraci.003.png
[ref3]: 3_client_dbeaver_installaci_i_confiuraci.004.png
