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

[« Anterior](exercicis.md)
# <a name="main"></a>**Autoavaluació**
![ref1]
## **Elecció múltiple**
### **Qüestió**
Després del procés de normalització, normalment el número de taules resultants és: 
#### **Respostes**
[Opció 1](#answer-13_5)![ref2]

<a name="answer-13_5"></a>Superior 

[Opció 2](#answer-13_41)![ref2]

<a name="answer-13_41"></a>Igual 

[Opció 3](#answer-13_44)![ref2]

<a name="answer-13_44"></a>No té res a veure, és independent 

[Opció 4](#answer-13_59)![ref2]

<a name="answer-13_59"></a>Inferior 
#### **Realimentació**
<a name="sa0b13_2"></a>Correcte !!! 

<a name="sa1b13_2"></a>NOOOOOOOO !!! 

<a name="sa2b13_2"></a>NOOOOOOOO !!! 

<a name="sa3b13_2"></a>NOOOOOOOO !!! 
#### **Solució**
1. [Opció correcta](#answer-13_5) ([Realimentació](#sa0b13_2))
1. [Incorrecte](#answer-13_41) ([Realimentació](#sa1b13_2))
1. [Incorrecte](#answer-13_44) ([Realimentació](#sa2b13_2))
1. [Incorrecte](#answer-13_59) ([Realimentació](#sa3b13_2))

![ref1]
## **Elecció múltiple**
### **Qüestió**
La dependència funcional entre 2 atributs, A i B, i que representem com A → B, significa: 
#### **Respostes**
[Opció 1](#answer-15_5)![ref2]

<a name="answer-15_5"></a>que per cada valor de B només en tenim un de A 

[Opció 2](#answer-15_50)![ref2]

<a name="answer-15_50"></a>que per cada valor de A només en tenim un de B 

[Opció 3](#answer-15_53)![ref2]

<a name="answer-15_53"></a>que B depén de la funció que tinga A en la taula (com per exemple si és clau principal) 







[Opció 4](#answer-15_56)![ref2]

<a name="answer-15_56"></a>cap de les anteriors 
#### **Realimentació**
<a name="sa0b15_2"></a>NOOOOOOOOO!!!! 

<a name="sa1b15_2"></a>CORRECTE !! 

<a name="sa2b15_2"></a>NOOOOOOOOO!!!! 

<a name="sa3b15_2"></a>NOOOOOOOOO!!!! 
#### **Solució**
1. [Incorrecte](#answer-15_5) ([Realimentació](#sa0b15_2))
1. [Opció correcta](#answer-15_50) ([Realimentació](#sa1b15_2))
1. [Incorrecte](#answer-15_53) ([Realimentació](#sa2b15_2))
1. [Incorrecte](#answer-15_56) ([Realimentació](#sa3b15_2))

![ref1]
## **Elecció múltiple**
### **Qüestió**
Suposem una taula per a guardar les FACTURES d'una empresa. En ella tindrem, entre d'altres, dos atributs: num\_fact i data\_fact. Quina dependència funcional penseu que tindrem entre ells? 
#### **Respostes**
[Opció 1](#answer-16_5)![ref2]

<a name="answer-16_5"></a>num\_fact → data\_fact 

[Opció 2](#answer-16_62)![ref2]

<a name="answer-16_62"></a>data\_fact → num\_fact 

[Opció 3](#answer-16_65)![ref2]

<a name="answer-16_65"></a>num\_fact ↔ data\_fact 

[Opció 4](#answer-16_68)![ref2]

<a name="answer-16_68"></a>No hi ha cap dependència funcional 
#### **Realimentació**
<a name="sa0b16_2"></a>CORRECTE !! 

<a name="sa1b16_2"></a>NOOOOOOOOOO!!!!!!! 

<a name="sa2b16_2"></a>NOOOOOOOOOO!!!!!!! 

<a name="sa3b16_2"></a>NOOOOOOOOOO!!!!!!! 
#### **Solució**
1. [Opció correcta](#answer-16_5) ([Realimentació](#sa0b16_2))
1. [Incorrecte](#answer-16_62) ([Realimentació](#sa1b16_2))
1. [Incorrecte](#answer-16_65) ([Realimentació](#sa2b16_2))
1. [Incorrecte](#answer-16_68) ([Realimentació](#sa3b16_2))

![ref1]
## **Elecció múltiple**
### **Qüestió**
I quina dependència funcional hi haurà entre data\_fact i num\_client? 
#### **Respostes**
[Opció 1](#answer-17_5)![ref2]

<a name="answer-17_5"></a>data\_fact → num\_client 

[Opció 2](#answer-17_71)![ref2]

<a name="answer-17_71"></a>num\_client → data\_fact 

[Opció 3](#answer-17_74)![ref2]

<a name="answer-17_74"></a>data\_fact ↔ num\_client 

[Opció 4](#answer-17_77)![ref2]

<a name="answer-17_77"></a>No hi ha cap dependència funcional 
#### **Realimentació**
<a name="sa0b17_2"></a>NOOOOOOOOOO!!!!!!! 

<a name="sa1b17_2"></a>NOOOOOOOOOO!!!!!!! 

<a name="sa2b17_2"></a>NOOOOOOOOOO!!!!!!! 

<a name="sa3b17_2"></a>CORRECTE !! 
#### **Solució**
1. [Incorrecte](#answer-17_5) ([Realimentació](#sa0b17_2))
1. [Incorrecte](#answer-17_71) ([Realimentació](#sa1b17_2))
1. [Incorrecte](#answer-17_74) ([Realimentació](#sa2b17_2))
1. [Opció correcta](#answer-17_77) ([Realimentació](#sa3b17_2))

![ref1]
## **Elecció múltiple**
### **Qüestió**


|De quina manera normalitzaries la següent taula: |![ref3]|
| :- | :- |


#### **Respostes**
[Opció 1](#answer-14_50)![ref2]

![ref4]

<a name="answer-14_50"></a>[Opció 2](#answer-14_54)![ref2]

![ref4]

<a name="answer-14_54"></a>[Opció 3](#answer-14_58)![ref2]

![ref4]
#### <a name="answer-14_58"></a>**Realimentació**
<a name="sa0b14_47"></a>NOOOOOOOOO !!!! 

<a name="sa1b14_47"></a>NOOOOOOOOO !!!! 

<a name="sa2b14_47"></a>CORRECTE ! 
#### **Solució**
1. [Incorrecte](#answer-14_50) ([Realimentació](#sa0b14_47))
1. [Incorrecte](#answer-14_54) ([Realimentació](#sa1b14_47))
1. [Opció correcta](#answer-14_58) ([Realimentació](#sa2b14_47))

[« Anterior](exercicis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 3.0](http://creativecommons.org/licenses/by-nc-nd/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: autoavaluaci.002.png
[ref2]: autoavaluaci.003.png
[ref3]: autoavaluaci.004.png
[ref4]: autoavaluaci.005.png
