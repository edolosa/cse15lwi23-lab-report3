# **Lab Report 3 - Researching Commands**
***

## Command: grep

For all the following commands, I used ChatGPT open AI with the prompt, "what other capabilities does the grep command have in bash".

ChatGPT responded with a description of grep followed by 7 different capabilities that it contains. A picture of the input and response will be at the bottom.

```
$ grep -rl Maple written_2

written_2/travel_guides/berlitz2/Canada-WhereToGo.txt

$ grep -rl Hawaii written_2  

written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
```

In these code snippets, we use the additional command `-rl` to the command `$grep`. `-r` causes grep to run recursively on the entire file that's given.
`-l` allows grep to return just the files that it finds the text that we gave it. Putting those commands together we are allowed to search for
all the files that contains the string we gave it.

```
$ grep -c Maple written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
2

$ grep -c Hawaii written_2/travel_guides/berlitz1/HandRHawaii.txt
9
```

From these examples, we see the use of the `-c` command. This command will show the count of all the lines that contain the given string. This can be useful
when we want to change a name of something within our file and we can use this command to keep checking if there are any instances left of the name.

``` 
$grep -rn Maple written_2

written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:131:Canadian Collections. Besides some classics of the 19th century evoking the life and landscapes of the early settlement, the best works are from Tom Thomson and the Group of Seven (see page 63). Look for Thomson’s Jack Pine, A. Y. Jackson’s Red Maple, Lawren Harris’s North Shore, Lake Superior, murals by Thomson, Arthur Lismer, and J. E. H. MacDonald, and Emily Carr’s Indian Hut, Queen Charlotte Islands. Inuit Art has some impressive sculpture, prints, and drawings from the 1950s and 1960s. The museum also houses the reconstructed Rideau Convent Chapel, a fine example of French-Canadian 19th-century architecture.
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:380:Duly renewed, then, make your way towards the harbor and railyards, to Gastown (between Water and Hastings), the resuscitated red-brick, cobbled-street district of Vancouver’s beginnings. This huckster’s paradise of boutiques, souvenir shops, bars, and restaurants is frankly commercial in its polished quaintness, but with a certain corny charm. At the west end of Water Street is the world’s first (and probably only) monumental steam-powered clock, signaling the hours with a resounding whistle. On Maple Street, a no less handsome statue of Gassy Jack, a distinctly derelict-looking riverboat captain known to his mother as John Deighton, stands on a whisky barrel symbolizing the drinks he served to lumbermen, persuading them to build the town in 1867.


$ grep -rn Lucayans  written_2

written_2/travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
Here we use the recursive command as well as `-n` which will give us the line number in the file after printing out the file that contains the string content. This can be useful if we want to go into the file and find the line quickly so we may look at the lines before and after the line we were searching for.

```
$ grep -rv 'the' written_2/travel_guides/berlitz2/Paris-WhatToDo.txt

What to Do
Shopping
If you’re pining for English-language books, Village Voice on rue Princesse in St-Germain-des-Prés is outstanding, but try, too, Brentano’s at 37 avenue de l’Opéra, or W. H. Smith at 248 rue de Rivoli.
The flower market on place Louis Lépine, near Notre-Dame on Ile de la Cité, opens from 8am to 7:30pm daily. On Sundays it switches to small pets, especially caged birds. The flower stalls on place de la Madeleine open daily except Monday.
Sports
Entertainment
Paris for Children

$ grep -rv 'a' written_2/travel_guides/berlitz2/Vallarta-History.txt

A Brief History
```

In this segment, we used the recursive command as well as the `-v` command which this time returns all lines that do not contain the given string.
In the first example we searched for lines that do not contain the word 'the' and we got a lot of lines. The second example we search for lines without the letter 'a'.
Notice how we a line that has uppercase a was returned. This means that the `-v` command is case sensitive.

***

![Image](https://media.discordapp.net/attachments/717860504093327450/1074788786006917160/image.png?width=763&height=663).

