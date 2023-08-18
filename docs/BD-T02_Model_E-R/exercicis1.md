
![ref1]
## **Exercici 3**
Dissenyar un esquema E/R que arreplegue informació sobre una universitat. Es considera que: 

- Els departaments (com per exemple el Departament de *Llenguatges i Sistemes Informàtics*) poden estar en una única facultat o ser interfacultatius, agrupant en aquest cas càtedres que pertanyen a facultats distintes.

- Una càtedra (per exemple la de *Bases de Dades*) pertany a un únic departament.

- Una càtedra està en una única facultat.

- Un professor està sempre assignat a un únic departament i adscrit a una o més d'una càtedra. Pot canviar de càtedra però no de departament. Ens interessa la data en què un professor és adscrit a una càtedra.

- Existeixen àrees de coneixement (com per exemple l'àrea d'*Informàtica*, que inclou els departaments de *Llenguatges i Sistemes Informàtics* i de *Enginyeria i Ciència dels Computadors*) i tot departament tindrà una única àrea de coneixement.

![ref1]
## **Exercici 4**
L'anàlisi de requisits d'una determinada xarxa bancària és el següent:

- De cada banc ens interessa el nom i l'adreça de la seu social. Hi ha un codi distint per a cada entitat bancària.
- Cada banc té distintes sucursal, que s'identifiquen *internament* per un codi.
- Cada sucursal té assignats una sèrie de comptes corrents, que s'identifiquen *internament* per un codi. Un compte pot pertànyer a un o més d'un client. És possible que cada client puga fer operacions distintes amb els comptes. Així podria ser que, encara que dos clients siguen titulars d'un mateix compte, només un tinga facultat per tancar-lo.
- Cada client, que s'identifica pel seu DNI, pot tenir més d'un compte, i evidentment privilegis distints en cadascun d'ells.
- Cada compte pot tenir domiciliacions associades a ell.
- Les sucursals poden atorgar préstecs als clients, que no estaran associats als comptes. Cada préstec s'atorga a nom d'un únic client, i a un client se li pot atorgar més d'un préstec.

![ref1]
## **Exercici 5**
Es vol mantenir informació sobre una **biblioteca**, on podem tenir de cada llibre més d'un exemplar, que a més es poden prestar, i que també ens interessa un històric de préstecs. L'anàlisi de requeriments seria el següent:

- Cada llibre (amb un determinat títol, ISBN, idioma, número d'edició i data d'edició) tracta només d'un tema, està editat per una única editorial, escrit per un o més autors, i disposarem d'uns quants exemplars. Dels exemplars sempre tindrem el número de registre, que l'identifica unívocament.
- Els préstecs són dels exemplars dels llibres, que són les materialitzacions dels llibres. Un exemplar es pot prestar a un únic lector (del qual tindrem Dni, Nom, Adreça i Telèfon), i ens interessa la data en la qual s'ha prestat. Un lector pot tenir més d'un llibre prestat.
- A banda del préstec actual, voldrem saber en el passat a qui s'ha prestat. Per tant en l'històric de préstecs cada exemplar s'haurà prestat a molts lectors, i per a poder dur el seguiment ens interessa la data de préstec i la de tornada.

![ref1]
## **Exercici 6**
Realitzeu l'esquema E/R que arreplegue informació d'una associació d'afeccionats a les **papallones**, que volen guardar informació respecte a exemplars capturats bé per a la seua observació, bé per a ser inclosos en una col·lecció: 

- Com en qualsevol ordre natural, un exemplar de papallona pertany a una espècie única. Una espècie pertany a un gènere únic, i un gènere a una família natural única.

- Cada espècie de papallona té un nom científic únic, encara que el seu nom comú, que depèn de la comarca on s'ha agafat, també ens interessa.

- Ja siga per a l'observació o per a formar part d'una col·lecció, primer s'ha de capturar l'exemplar de papallona. Aquesta captura la realitza una única persona, i voldrem saber també en quin lloc (comarca) s'ha capturat. Si l'exemplar és destinat a l'observació voldrem saber la durada de l'observació.

- Una determinada persona només pot ser propietària d'una col·lecció, però els exemplars d'aquesta col·lecció poden haver estat capturats per altres persones.

- Es vol mantenir informació de les famílies, gèneres i espècies de papallones encara que no s'hagen capturat exemplars dels mateixos.

- Una papallona només pot pertànyer a una col·lecció, i una col·lecció està formada almenys per un exemplar. Tota papallona que pertany a una col·lecció tindrà un determinat valor. 

![ref1]
## **Exercici 7**
Una empresa de línies ferroviàries vol que se li dissenye una Base de Dades per a la seua gestió. Aquesta és l'anàlisi de requeriments:



- La companyia necessita controlar els trens, els seus treballadors i els viatges realitzats. 
- Dels treballadors es vol guardar el seu codi i nom. Per als conductors, a més a més, ens interessa el número d'hores que han realitzat.
- Tots els treballadors tenen una estació base a la qual pertanyen i de les estacions es vol tenir el nom, la localitat i el telèfon.
- Els trens tenen un codi que els identifica, un tipus (rodalies, grans línies,…) i una estació on se li realitzen les revisions de manteniment.
- Un trajecte serà un tipus de viatge que es realitza regularment. Tindrà una estació origen i una estació de destí.
- Un viatge de tren és una materialització d'un trajecte, i utilitzarà òbviament un tren, una data, una hora d'eixida i un o uns conductors que el porten (no ens interessen els altres possibles treballadors que van en els viatges). Tots els viatges s'identifiquen per un codi, per exemple, el viatge corresponent al trajecte Castelló - València de les 12:10 d'un determinat dia és el viatge 4356.

Opcionalment, podem posar totes les estacions a les quals s'arriba en un trajecte (substituint l'estació origen i destí). Haurem de saber si l'estació és origen, destí o de pas.

[« Anterior](7_restriccions_externes.md) | [Següent »](informaci_addicional.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis1.002.png
