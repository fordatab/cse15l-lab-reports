grep
======
-c :
```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/non-fiction/OUP/Abernathy
$ grep -c "bot" ch1.txt
6
```
Counts the number of lines that contains the string "bot" and it is useful 
for counting substrings.
```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/non-fiction/OUP
$ grep -c "ratio" Abernathy/*
Abernathy/ch1.txt:20
Abernathy/ch14.txt:18
Abernathy/ch15.txt:21
Abernathy/ch2.txt:26
Abernathy/ch3.txt:13
Abernathy/ch6.txt:8
Abernathy/ch7.txt:16
Abernathy/ch8.txt:22
Abernathy/ch9.txt:20
```
It also can count the number of lines with the string "ratio" for each file 
in the directory ```Abernathy/````` and prints the number of lines next to each file 
name. It is useful because all the information in the directory can be 
seen from one command.

-l :
```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/travel_guides
$ grep -l "History" berlitz2/*
berlitz2/Algarve-History.txt
berlitz2/Amsterdam-History.txt
berlitz2/Athens-History.txt
berlitz2/Bahamas-History.txt
berlitz2/Bali-History.txt
berlitz2/Barcelona-History.txt
berlitz2/Barcelona-WhereToGo.txt
berlitz2/Beijing-History.txt
berlitz2/Beijing-WhereToGo.txt
berlitz2/Berlin-History.txt
berlitz2/Berlin-WhereToGo.txt
berlitz2/Bermuda-WhereToGo.txt
berlitz2/Bermuda-history.txt
berlitz2/Boston-WhereToGo.txt
berlitz2/Budapest-History.txt
berlitz2/Budapest-WhatToDo.txt
berlitz2/Budapest-WhereoGo.txt
berlitz2/California-History.txt
berlitz2/California-WhereToGo.txt
berlitz2/Canada-WhereToGo.txt
berlitz2/CanaryIslands-History.txt
berlitz2/CanaryIslands-WhereToGo.txt
berlitz2/Cancun-History.txt
berlitz2/Cancun-WhereToGo.txt
berlitz2/China-History.txt
berlitz2/China-WhereToGo.txt
berlitz2/Costa-History.txt
berlitz2/CostaBlanca-History.txt
berlitz2/Crete-History.txt
berlitz2/Crete-WhereToGo.txt
berlitz2/Cuba-History.txt
berlitz2/NewOrleans-History.txt
berlitz2/Portugal-History.txt
berlitz2/PuertoRico-WhereToGo.txt
berlitz2/Vallarta-History.txt
```
Prints all the files that contains the word "History". It is useful because 
it suppresses all the lines that contains the word "History" and shows the 
files which is less clutter.

```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2
$ grep -l "fun" travel_guides/*/* | wc -l
109
```
Counts the number of files in ```travel_guides/``` that contains the word "fun" 
using a pipe to do ```wc```. This is useful for counting files concisely 
without output spam.

-i :
```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/non-fiction/OUP/Berk
$ grep -o -i "Dog"  CH4.txt
dog
dog
dog
dog
```
Prints all occurrences of the string "Dog" but without case distinction and 
-o shows that "dog" is matched using -i. It is useful because words at the 
beginning of a sentence are capitalized and can therefore be counted too easily.

```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/non-fiction/OUP
$ find Kauffman/* | grep -i -c "ch"
9
```
Counts the number of files that are chapters using ```find``` and -i because 
some are named "CH" and -i allows to search for all cases of "ch". 

-w
```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main/written_2/non-fiction/OUP/Rybczynski
$ grep -w -c "at" *
ch1.txt:16
ch2.txt:15
ch3.txt:17
```
Counts the number of lines with that contains the word "at", not including 
substrings. This is useful because the other options may match a word which 
is a substring of another one and -w prevents that.

```ugcir@LAPTOP-I6PBA9AM MINGW64 ~/Downloads/docsearch-main/docsearch-main
$ grep -w -r -l -i "lucayans" written_2/
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Find the file that contains the word "lucayans" in ```written_2```. It is 
useful because using four options can reliably search for a file that 
contains a word for any directory and word given. 

[Source for all commands](https://linuxcommand.org/lc3_man_pages/grep1.html)