# Lab3 Report 
## Command 1 : `grep "pattern" /path/to/directory/*.txt`
This command search for a pattern in all the .txt files in a given path and return the line containing the pattern. 

**Example 1**

```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:308$ grep "[0-9],[0-9][0-9][0-9][0-9]" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:        The main or Great Cave is a hollow 400 m (1,1312 ft) up in
```

In this example, the pattern that is being search are five digit numbers with the first and second digit separated by a comma. There is only one matching number in this path `written_2/travel_guides/berlitz1` that is 1,1312. This is useful becasue someone can use this to, for example, search for all the phone numbers in a bunch of documents. 

**Example 2**

```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:315$ grep "[A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z][A-Z]" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt:        HISTORICAL LANDMARKS
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt:        ENTERTAINMENT
written_2/travel_guides/berlitz1/WhatToMadeira.txt:        ENTERTAINMENT
written_2/travel_guides/berlitz1/WhereToFWI.txt:        MARTINIQUE
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:        EXCURSIONS
```
In this example, the pattern that is being searched is a all-capital word with length more than 10 letters. The results shows 5 matching words in  `written_2/travel_guides/berlitz1`. This is useful since someone might forget the word they want to search but still remember the pattern. In this way, the person can still get their answer. 

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

The command is trying to search "Flamboyant" in the path written_2/travel_guides/berlitz1. As can been seen in the results, in addition to the line and the file path, the line number where the word appears is shown. This is useful since if the document is long, one can quickly locate the line they want to read and skip to there. 

**Example 4**
```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:328$ grep -n "1350" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt:535:        c.1350 b.c. , and embellished by Ramses II in the 19th Dynasty. The   
```
The command is trying to search the number 1350 in the path `written_2/travel_guides/berlitz1`. As can been seen in the results, it appears in line 535 at `written_2/travel_guides/berlitz1/WhereToEgypt.txt`. This is useful since if the document is long, one can quickly locate the line they want to read and skip to there. 


## Command 3: `grep -C number "word" filename.txt`
This command shows the context near the searched lines. Specifically, it shows the input number of lines above and below the line containing target word.

**Example 5**
```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:330$ grep -C 2 "1350" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt-        In the heart of the modern town, set beside the waters of
written_2/travel_guides/berlitz1/WhereToEgypt.txt-        the Nile, is Luxor Temple, started by Amenophis III in the 18th Dynasty    
written_2/travel_guides/berlitz1/WhereToEgypt.txt:        c.1350 b.c. , and embellished by Ramses II in the 19th Dynasty. The        
written_2/travel_guides/berlitz1/WhereToEgypt.txt-        temple served a specific purpose, to host the New Year celebration to      
written_2/travel_guides/berlitz1/WhereToEgypt.txt-        the God Amun who would be represented in both his positive form, Amun     
```
The command is trying to search for the number 1350 in `written_2/travel_guides/berlitz1/*.txt` and show two lines above and below the line containing the number. This can also be seen in the results that there are in total five lines and the line with 1350 is in the middle. This is useful because someone might want to get the information in the article that contains the word they want to search and one line may given enough information. 

**Example 6**
```
[cs15lwi23ajj@ieng6-202]:skill-demo1-data:333$ grep -C 1 "1,1312" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt-        nests and hornbill ivory for Chinese porcelain and beads.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:        The main or Great Cave is a hollow 400 m (1,1312 ft) up in
written_2/travel_guides/berlitz1/WhereToMalaysia.txt-        the sandstone Subis plateau. Besides some giant crickets and scorpions 
```
The command is trying to search for the number 1,1312 in `written_2/travel_guides/berlitz1/*.txt` and show one line above and below the line containing the number. This is also useful because the number of line customizable. If the user feels that there isn't enough information, they could enlarge the context. Some users might not line to read a long paragraph so they only shows one line above and below, like this example. 

## Command 4: 
