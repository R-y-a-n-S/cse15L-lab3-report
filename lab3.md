# Lab3 Report 
## Command 1 : `grep "pattern" /path/to/directory/*.txt`
This command search for a pattern in all the .txt files in a given path and return the line containing the pattern. 

**Example 1**

```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:308$ grep "[0-9],[0-9][0-9][0-9][0-9]" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:        The main or Great Cave is a hollow 400 m (1,1312 ft) up in
```

In this example, the pattern that is being search are five digit numbers with the first and second digit separated by a comma. There is only one matching number in this path `written_2/travel_guides/berlitz1` that is 1,1312

**Example 2**

```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:315$ grep "[A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z]" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt:        HISTORICAL LANDMARKS
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:        ENTERTAINMENT
written_2/travel_guides/berlitz1/WhatToMadeira.txt:        ENTERTAINMENT
written_2/travel_guides/berlitz1/WhereToFWI.txt:        MARTINIQUE
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:        EXCURSIONS
```
In this example, the pattern that is being searched is a all-capital word with length more than 10 letters. The results shows 5 matching words in  `written_2/travel_guides/berlitz1`

## Command 2 : `grep -n "word" /path/to/directory/*.txt`
This command search the word in all the .txt files in the path and return the the line as well as the line number

**Example 3**
```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:322$ grep -n "Flamboyant" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt:377:        Milan’s new Flamboyant Gothic cathedral, which took centuries to       
written_2/travel_guides/berlitz1/WhereToFrance.txt:1371:        Inside stands a formidable Flamboyant Gothic pulpit, built
written_2/travel_guides/berlitz1/WhereToFrance.txt:1935:        Beurre, is Flamboyant Gothic of the 15th century. According to local 
written_2/travel_guides/berlitz1/WhereToFrance.txt:1963:        Flamboyant Goth­ic architecture built on the site of the medieval    
written_2/travel_guides/berlitz1/WhereToFrance.txt:2178:        markedly lighter and more airy Flamboyant Gothic chancel. The choir and
written_2/travel_guides/berlitz1/WhereToFrance.txt:2440:        1500 and a masterpiece of Flamboyant Gothic style.
written_2/travel_guides/berlitz1/WhereToFrance.txt:3499:        The dimensions of the gigantic Flamboyant Gothic
written_2/travel_guides/berlitz1/WhereToItaly.txt:2166:        Flamboyant Gothic building fronts the Piazzetta and the basin, the    
written_2/travel_guides/berlitz1/WhereToItaly.txt:2396:        Flamboyant Gothic design has a flair and grace that bewitch you into  
written_2/travel_guides/berlitz1/WhereToItaly.txt:2881:        Italy’s Flamboyant Gothic cathedrals. Teams of Italian, French,       
written_2/travel_guides/berlitz1/WhereToItaly.txt:3044:        church is a high point in the transition from Flamboyant Gothic to 
```

The command is trying to search "Flamboyant" in the path written_2/travel_guides/berlitz1. As can been seen in the results, in addition to the line and the file path, the line number where the word appears is shown. 

**Example 4**
```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:328$ grep -n "1350" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt:535:        c.1350 b.c. , and embellished by Ramses II in the 19th Dynasty. The   
```
The command is trying to search the number 1350 in the path written_2/travel_guides/berlitz1. As can been seen in the results, it appears in line 535 at `written_2/travel_guides/berlitz1/WhereToEgypt.txt`.

## Command 3: `grep -C number "word" filename.txt`
This command shows the context near the searched lines. Specifically, it shows the input number of lines above and below the line containing target word.

**Example 5**
