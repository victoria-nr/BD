Bases de Dades

- [Tema 6: SQL - Consultes avançades (part II)](index.md)
- [2.1 Introducció](21_introducci.md)
- [2.2 Combinacions de taules](22_combinacions_de_taules.md) 
  - [2.2.1 Producte cartesià](221_producte_cartesi.md)
  - [2.2.2 Combinació interna](222_combinaci_interna.md) 
    - [Exercicis](exercicis.md)
  - [2.2.3 Combinació externa](223_combinaci_externa.md) 
    - [Exercicis](exercicis0.md)
- [2.3 Subconsultes](23_subconsultes.md) 
  - [Exercicis](exercicis1.md)
- [2.4 Consultes d'operacions de conjunts](24_consultes_doperacions_de_conjunts.md) 
  - [Exercicis](exercicis2.md)
- [Exercicis de tot el tema, amb els resultats](exercicis_de_tot_el_tema_amb_els_resultats.md)

[« Anterior](exercicis1.md) | [Següent »](exercicis2.md)
# <a name="main"></a>**2.4 Consultes d'operacions de conjunts**
Agruparem en aquest apartat les consultes que tracten conjunts de files per a fer operacions d'algebra de conjunts: **unió**, **intersecció** i  **diferència** de conjunts

Toters aquestes consultes ajunten els resultats de dues o més consultes.

Sintaxi de la UNIÓ

[TABLE] consulta1 
UNION [ALL] 
[TABLE] consulta2 ...

Cadascuna de les consultes pot ser una taula (posant la paraula **TABLE** davant) o el nom d'una consulta ja guardada, encara que el més habitual serà posar directament la **sentència SQL**.

Els requisits són que les dues (o més) consultes tornen el mateix nombre de camps, i que siguen sinó del mateix tipus, sí de tipus compatibles

Igual que en la unió de conjunts, el resultat seran totes les files de les dues (o més) consultes individuals, però sense repetir files, és a dir, si de les dues consultes s'obtenen files iguals, aquestes només eixiran una vegada. L'anterior es pot evitar si posem el predicat ALL, i aleshores sí que eixiran les files repetides.

Els noms dels camps vindran donats per la primera consulta.

Si volem ordenar per algun camp, ho haurem de posar al final de l'última consulta, però referint-se en tot cas als camps de la primera consulta (ho podem evitar posant el número d'ordre en el ORDER BY)

Exemple

1. Volem veure en un únic resultat tant el nom de les comarques com el nom de les poblacions, sempre amb el nom de la província al costat

SELECT nom\_c, provincia 
`    `FROM COMARQUES
UNION 
SELECT nom, provincia 
`    `FROM COMARQUES INNER JOIN POBLACIONS USING (nom\_c)
ORDER BY nom\_c;

Com a curiositat, eixiran 575 files, però si posàrem UNION ALL ens eixirien 576. Això és perquè la comarca de la ciutat de València es diu València i està a la província de València. Per tant és una fila que apareixerà tant en la primera com en la segona consulta. Si fem UNION no es repetirà, però si fem UNION ALL sí que es repetirà.

Sintaxi de la INTERSECCIÓ

És identica a la unió, però posant la paraula **INTERSECT**, i servirà per a traure únicament les files que estan en les dues consultes.

[TABLE] consulta1 
INTERSECT [ALL] 
[TABLE] consulta2 ...

Igual que abans, cadascuna de les consultes pot ser una taula (posant la paraula **TABLE** davant), i tenim el requisit que les dues (o més) consultes tornen el mateix nombre de camps, i de tipus compatibles.

En principi no eixiran files repetides, a no ser que posem **ALL**

Exemple

1. Com que en l'exemple de la unió havíem vist que la fila València València eixia en les 2 consultes, anem a comprovar que apareix en la intersecció:

SELECT nom\_c, provincia 
`    `FROM COMARQUES
INTERSECT
SELECT nom, provincia 
`    `FROM COMARQUES INNER JOIN POBLACIONS USING (nom\_c)
ORDER BY nom\_c;

Sintaxi de la DIFERÈNCIA

És identica a les anteriors, però posant la paraula **EXCEPT**, i servirà per a traure les files que estan en la primera consulta però que no estan en la segona.

[TABLE] consulta1 
EXCEPT [ALL] 
[TABLE] consulta2 ...

Igual que abans, cadascuna de les consultes pot ser una taula (posant la paraula **TABLE** davant), i tenim el requisit que les dues (o més) consultes tornen el mateix nombre de camps, i de tipus compatibles.

En principi no eixiran files repetides, a no ser que posem **ALL**

Exemple

1. Aprofitem el mateix exemple d'abans per a comprovar que amb EXCEPT no eixirà la comarca València, ja que hi ha una fila idèntica en la segona consulta:

SELECT nom\_c, provincia 
`    `FROM COMARQUES
EXCEPT
SELECT nom, provincia 
`    `FROM COMARQUES INNER JOIN POBLACIONS USING (nom\_c)
ORDER BY nom\_c;

[« Anterior](exercicis1.md) | [Següent »](exercicis2.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial SenseObraDerivada 2.5](http://creativecommons.org/licenses/by-nc-nd/2.5/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
