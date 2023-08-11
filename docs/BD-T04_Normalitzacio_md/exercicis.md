Bases de Dades

- [Tema 4: Normalització](index.md)
- [Objectius](objectius.md)
- [1. Introducció](1_introducci.md)
- [2. Primer Forma Normal (1FN)](2_primer_forma_normal_1fn.md)
- [3. Dependència Funcional](3_dependncia_funcional.md)
- [4. Segona Forma Normal (2FN)](4_segona_forma_normal_2fn.md)
- [5. Dependència Funcional Transitiva](5_dependncia_funcional_transitiva.md)
- [6. Tercera Forma Normal (3FN)](6_tercera_forma_normal_3fn.md)
- [7. Forma Normal Boyce-Codd (FNBC)](7_forma_normal_boycecodd_fnbc.md)
- [Resum](resum.md)
- [Exercicis](exercicis.md)
- [Autoavaluació](autoavaluaci.md)

[« Anterior](resum.md) | [Següent »](autoavaluaci.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercici 1**
Normalitzar la taula relacional que té com a graf de dependències funcionals el següent: 

![ref2]



Podeu normalitzar-ho tot directament, sense haver de passar primer per 2FN , 3FN i FNBC. 

![ref1]
## **Exercici 2**
En un Institut tenen distribuïda la informació en els següents fitxers:

|<p>**FGAL** </p><p>CODAL <br>NUMEX <br>COGNOM1 <br>COGNOM2 <br>NOM <br>CODCURS <br>NOMCURS</p>|<p>**FASSIGN**</p><p>CODCURS <br>CODASSIG <br>NOMCURS <br>NOMASSIG <br>CODPROF <br>NOMPROF</p>|<p>**FPROF**</p><p>CODPROF <br>NOMPROF <br>CODCURS1 <br>CODASSIG1 <br>CODCURS2 <br>CODASSIG2 <br>. <br>. <br>. <br>CODCURS10 <br>CODASSIG10</p>|<p>**FCURS**</p><p>CODCURS <br>NOMCURS <br>CODTUTOR <br>NOMTUTOR <br>CODASSIG1 <br>CODASSIG2 <br>. <br>. <br>. <br>CODASSIG17</p>|
| :-: | :-: | :-: | :-: |

Normalitzeu els fitxers, si els considerem taules d’una Base de Dades. Heu de parar especial atenció a veure si està en 1FN.

![ref1]
## **Exercici 3**
La factura d'un hotel és la següent:

||
| :- |

|HOTEL PRIMAVERA|| | |Factura:|1934|
| :- | :- | :- | :- | :- | :- |
|Data:|15 desembre 2009| | | | |
| | | | | | |
|Client:|Andreu Torlà Gomis| | |Habitació:|202|
|DNI:|18\.012.345-W| | |Tipus:|Doble|
|Domicili:|C/ Palanques, 5| | |Tarifa:|2|
|CP:|12004| | | | |
|Població:|Castelló| | | | |
|Telèfon:|964-223344| | | | |
| | | | | | |
|Núm. pers.:|2| | | | |
| | | | | | |
|Codi|Concepte|Quantitat|Preu unitari|Total| |
| | | | | | |
|2|Estància Mitja Pensió|3|65|195| |
|45|Dinar|2|15|30| |
|23|Consum Bar|1|5,3|5,3| |
| | | | | | |
| | | | | | |
| | | | | | |
| |Base imponible:|230,3| | | |
| |IVA (16%):|36,85| | | |
| | |----------| | | |
| |Total :|267,15| | | |

||
| :- |


Si considerem tota la informació en una única taula tindrem:

**FACTURA**

|NUMFACT <br>DATA <br>NUMHAB <br>TIPHAB <br>TARHAB <br>NOMCLI <br>DNICLI <br>ADRCLI <br>CPCLI <br>CIUCLI <br>TELCLI <br>NUMPERS|COD1 <br>CONCEPTE1 <br>QUANT1 <br>PREU1 <br>TOTAL1 <br>. <br>. <br>COD15 <br>CONCEPTE15 <br>QUANT15 <br>PREU15 <br>TOTAL15|TOTAL <br>IVA <br>TOTALIVA <br>TOTFAC|
| :- | :- | :- |

Intenteu normalitzar-la. Pareu especial atenció aveure si està en 1FN.

[« Anterior](resum.md) | [Següent »](autoavaluaci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis.002.png
[ref2]: exercicis.003.png
