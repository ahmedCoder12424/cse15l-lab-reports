# Options of Grep Command

[Source](/guides/content/editing-an-existing-page)

## 1. -l

This option outputs path of files with matching string. This is helpful because in the output file, we simply find which files contain the word rather than outputting all the content of the files. 

### Example #1

In this example, we are finding all files that contain the world Malaysia. Using the `-l` option here shows the list of files containing the word. If we
had excluded the option, then the all the content of each file would be displayed which would be much less readable. 

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:411$ xargs grep -l "Malaysia" < grep-results.txt > wordSearch.txt

```
__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:412$ cat wordSearch.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt
written_2/travel_guides/berlitz1/IntroMalaysia.txt
written_2/travel_guides/berlitz1/JungleMalaysia.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt

```

### Example #2

In this example, we use the option `-l` to search for the word "Bengal" which is not a name of any file and contained in the content of files. 
Once again, we see that the files are listed that contain rather the content of the files which makes the output very readable.

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:464$ xargs grep -l "Bengal" < grep-results.txt > wordSearch.txt

```
__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:465$ cat wordSearch.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt
written_2/travel_guides/berlitz1/IntroIndia.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz2/Nepal-History.txt
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt

```




## 2. -L

This option outputs path of files without matching string. This is essentially the inverse of -l command and can be helpful in finding files without a common string. 

### Example #1

In this example, I search for the files that don't include the word "war" using the `-L` option. Since the collection of files includes a lot about history, one would expect war to be a common word to be used in the files. This can be helpful in showing us which words are common and which files are more unique for not containing a common word. 

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:416$ xargs grep -L "war" < grep-results.txt > wordSearch.txt



```

__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:417$ cat wordSearch.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chO.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/JungleMalaysia.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt


```
### Example #2

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:418$ xargs grep -L "important" < grep-results.txt > wordSearch.txt

In this example, I used the `-L` option to search for files without the word "important" which results in a comparativley small number of files
confirming that "important" is a common word. 

```

__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:419$ cat wordSearch.txt
written_2/non-fiction/OUP/Castro/chO.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryMallorca.txt
written_2/travel_guides/berlitz1/IntroEdinburgh.txt


```





## 3. -c 

This option counts number of matching lines in input file. This is helpful for easily seeing how many matches each file contains. 

### Example #1

In this example, I search for the files containing the word "war" but with the `-c` option. This could be helpful if you wanted to search for files with most occurences of the word "war" to find the files that focus on war. 

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:422$ xargs grep -c "war" < grep-results.txt > wordSearch.txt 

```

__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:423$ cat wordSearch.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt:8
written_2/non-fiction/OUP/Abernathy/ch14.txt:4
written_2/non-fiction/OUP/Abernathy/ch15.txt:3
written_2/non-fiction/OUP/Abernathy/ch2.txt:7
written_2/non-fiction/OUP/Abernathy/ch3.txt:8
written_2/non-fiction/OUP/Abernathy/ch6.txt:4
written_2/non-fiction/OUP/Abernathy/ch7.txt:6
written_2/non-fiction/OUP/Abernathy/ch8.txt:6
written_2/non-fiction/OUP/Abernathy/ch9.txt:0
written_2/non-fiction/OUP/Berk/CH4.txt:27
written_2/non-fiction/OUP/Berk/ch1.txt:21
written_2/non-fiction/OUP/Berk/ch2.txt:34
written_2/non-fiction/OUP/Berk/ch7.txt:28


```


### Example #2

Similiarly, in this example, I am searching for the word "travel" with the `-c` option. This shows which files focus on travel since the ouput shows the number of occurences of "travel" in each file. 

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:426$ xargs grep -c "travel" < grep-results.txt > wordSearch.txt


```

__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:427$ cat wordSearch.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt:0
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:3
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:0
written_2/non-fiction/OUP/Abernathy/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch8.txt:0
written_2/non-fiction/OUP/Abernathy/ch9.txt:0
written_2/non-fiction/OUP/Berk/CH4.txt:4
written_2/non-fiction/OUP/Berk/ch1.txt:0
written_2/non-fiction/OUP/Berk/ch2.txt:0
written_2/non-fiction/OUP/Berk/ch7.txt:0
written_2/non-fiction/OUP/Castro/chA.txt:1
written_2/non-fiction/OUP/Castro/chB.txt:1
written_2/non-fiction/OUP/Castro/chC.txt:1
written_2/non-fiction/OUP/Castro/chL.txt:2
written_2/non-fiction/OUP/Castro/chM.txt:2

```
## 4. -n

This option causes each line of output to contain the line number of each line containing string. This helps us locate where in each of the files contain matching stings. 

### Example #1

In this example, I am searching for the word "Lucayans" using the `-n` option. Since the file is large, the output helps us easily locate where "Lucayans" is in the file on lines 6 and 7. 

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:458$ xargs grep -n "Lucayans" < grep-results.txt > wordSearch.txt 


```
__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:459$ cat wordSearch.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.



```
### Example #2

This example searches for "Malaysia" using the `-n` option and gives precise location of the word in all the files containing it. This is very detailed ouptut which can help us if we wanted to perform such a deep search for "Malaysia"

__command:__
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:460$ xargs grep -n "Malaysia" < grep-results.txt > wordSearch.txt

```
__output:__ 
```
[cs15lwi23axu@ieng6-202]:skill-demo1-data:461$ cat wordSearch.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:9:        might have made Malaysia an inviting place for the contemporaries of
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:163:        elections in modern federal Malaysia. Their confederation of States
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:213:        including Java and Sumatra, went to the Dutch. Peninsular Malaysia and
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:354:        on Pearl Harbor, on Malaysia’s east coast, near Kota Bharu. It was
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:455:        the new name of Malaysia in September 1963, but Singapore soon clashed
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:479:        Bahasa Malaysia, was also officially encouraged.
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:483:        position, which came as Malaysian exports were also growing. Combined
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:487:        Malaysia has achieved remarkable prosperity as the economy built on the
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:495:        the 1970s and 1980s brought valuable revenue to Malaysia as a whole and
written_2/travel_guides/berlitz1/HistoryMalaysia.txt:505:        Malaysia enters the next millennium a wealthy and
written_2/travel_guides/berlitz1/IntroMalaysia.txt:7:        As Malaysia has moved resolutely into the modern age, it has
written_2/travel_guides/berlitz1/IntroMalaysia.txt:11:        and wide expressways, Malaysia is set to exceed visitors’
written_2/travel_guides/berlitz1/IntroMalaysia.txt:22:        Your gateway to Malaysia will probably be through its
written_2/travel_guides/berlitz1/IntroMalaysia.txt:26:        Malaysia is divided into two major regions: the peninsula,
written_2/travel_guides/berlitz1/IntroMalaysia.txt:28:        and East Malaysia, whose two provinces, Sabah and Sawarak, are located
written_2/travel_guides/berlitz1/IntroMalaysia.txt:33:        especially on the West coast, while East Malaysia is dominated by the
written_2/travel_guides/berlitz1/IntroMalaysia.txt:34:        country’s characteristic impenetrable jungle. Malaysia’s two parts
written_2/travel_guides/berlitz1/IntroMalaysia.txt:37:        Malaysia’s relative wealth is reflected in the excellent
written_2/travel_guides/berlitz1/IntroMalaysia.txt:41:        Malaysians live in townships of more than 5,000 inhabitants, an
written_2/travel_guides/berlitz1/IntroMalaysia.txt:59:        peninsula. Malaysia rose first as a trading point for Asia and Europe,
written_2/travel_guides/berlitz1/IntroMalaysia.txt:74:        On the great island of Borneo, East Malaysia’s states of
written_2/travel_guides/berlitz1/IntroMalaysia.txt:92:        Malaysia can be proud of a unique achievement — the coexistence of the
written_2/travel_guides/berlitz1/IntroMalaysia.txt:102:        Malaysia — as the national language, Malays enjoy practically exclusive
written_2/travel_guides/berlitz1/IntroMalaysia.txt:120:        Economic development has given younger Malaysians wider
written_2/travel_guides/berlitz1/JungleMalaysia.txt:7:        To go to Malaysia without setting foot in the jungle would
written_2/travel_guides/berlitz1/JungleMalaysia.txt:55:        animals of the Malaysian jungle are not very conspicuous. Tigers and
written_2/travel_guides/berlitz1/JungleMalaysia.txt:57:        Malaysia are the smallest of their kind.
written_2/travel_guides/berlitz1/JungleMalaysia.txt:75:        Malaysian deer is the brown antlered sambar. Another shy creature, you
written_2/travel_guides/berlitz1/JungleMalaysia.txt:79:        Tiger. The few Malaysian tigers left roaming the peninsula
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:8:        Malaysia. You will probably want to take time to shop for traditional
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:13:        vacation just sampling the local shopping scene. And Malaysia offers a
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:17:        A variety of goods are available throughout Malaysia. Large
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:28:        Malaysia’s tax havens are Pulau Langkawi and Labuan.
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:36:        over the peninsula and East Malaysia. KL’s Central Market gives you a
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:100:        pieces of indigenous workmanship in all of Malaysia. Really good ones
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:179:        Malaysia’s traditional entertainment is more often than not
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:182:        information can also be found at the Malaysian Tourist Information
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:216:        Malaysians love celebrating, and with so many different
written_2/travel_guides/berlitz1/WhatToMalaysia.txt:276:        Christmas Day: Celebrated throughout Malaysia as a national
written_2/travel_guides/berlitz1/WhereToIndia.txt:2099:        with their spices and ivory to Burma, Malaysia, Cambodia, and Java.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:7:        Setting your priorities in Malaysia before you start out is
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:9:        many destinations in Malaysia offer a key activity travelers will be
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:10:        searching for, such as exploring Malaysia’s culture and history or
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:14:        Malaysia’s well developed transportation
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:22:        detailed practical information on how to handle your stay in Malaysia.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:27:        The towns hold a mirror to Malaysia’s ethnic blend of Malay,
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:30:        Lumpur. (In true Malaysian style, we will refer to the capital by its
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:31:        abbreviation, KL. ) The northeast coast of Malaysia, especially between
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:34:        kampungs (villages) of the interior. Step back into Malaysia’s history
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:45:        Chinatowns throughout Malaysia offer chances to explore, browse, or
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:55:        enjoy the rural and forested Malaysia. But finding your way around the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:61:        of the rainforest. Offices of the Malaysian Tourist Development
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:66:        Malaysia has done a fine job of giving visitors access to
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:84:        Malaysia the offerings are plenty. Whether on the Peninsula or at the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:93:        resorts of Tioman Island and Desaru. In East Malaysia, Kuching and Kota
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:96:        Though the official tongue is Malay, or Bahasa Malaysia,
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:105:        Malaysia’s prosperity in recent decades is most evident in
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:108:        seen driving Malaysian-made Proton sedans on six-lane highways — all
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:121:        Malaysian families for holiday entertainment, a far cry from the more
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:140:        As in other Malaysian cities, the population is
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:155:        find Infokraf, where the Malaysian Handicraft Development Corporation
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:177:        whose work is reflected in the Malaysian Railway buildings and
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:196:        over a buff-tiled floor. Clothes and Malaysian arts and crafts have
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:243:        (National Art Gallery) of Malaysian and foreign art. West of the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:249:        symbolize the 13 states of Malaysia and 5 pillars of Islamic faith. The
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:258:        flanking the entrance depict themes of Malaysia’s culture and history.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:264:        as a 40,000-year-old homo sapiens skull. The older Royal Malaysian
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:267:        the campus of the University of Malaysia is the Asian Art Museum, with
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:284:        road, the Tugu Negara (National Monument) commemorates Malaysia’s
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:305:        is a one-stop center of the Malaysian Tourist Information Complex.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:316:        to the centerpiece of Malaysia’s site for the 1998 Commonwealth Games.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:322:        Malaysia for good deals, excellent local food, and just plain
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:332:        As prosperity has taken hold in Malaysia, so too has the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:363:        Malaysian rainforest for those with little time to venture into the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:374:        By the time Malaysia came under the British imperial sway,
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:380:        Nowadays, Malaysian families are lured to the highlands closest to
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:399:        casino is Malaysia’s only such legal gambling house, with strict dress
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:406:        Malaysia’s business set. The resort was named after Louis James Fraser,
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:430:        the Malaysian Nature Society supports an “international bird race,”
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:486:        of the walks pass through — or close to — the Malaysian Agriculture
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:500:        the key region for Malaysia’s economic prosperity, standing as a lure
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:506:        Malaysia’s second largest state, reaching from Tanjung Malim in the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:513:        the second largest city in Malaysia, while Kuala Kangsar is the royal
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:538:        the best preserved examples of Chinese architecture in Malaysia. For
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:558:        in Teluk Intan, is Malaysia’s equivalent of the leaning tower of Pisa.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:567:        is also where Malaysia’s rubber industry started with the planting of
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:598:        Malaysia. On the way, you will pass the prison, used by the Japanese in
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:601:        executions of Malaysia’s drug offenders.
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:610:        Malaysia’s smallest and oldest hill station and the retreat for
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:636:        for Malaysia. Armed with an entry permit, visitors make first for the
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:657:        Malaysian currency. (For your trekking requirements, see page 181. )
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:709:        many ways this is the story of southwestern Malaysia’s southwest
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:744:        from KL, was Malaysia’s first city, built on the trading empires of
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:849:        in Malaysia. Dedicated to Kuan Yin, it is flamboyantly decorated with
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:930:        the future George IV. Nowadays, it is the third largest of Malaysia’s
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1112:        prove disappointing to those who have travelled on Malaysia’s
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1129:        traditional architecture from elsewhere in Malaysia. At the southern
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1162:        State, heads into the rice bowl of Malaysia, as seas of green spread
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1201:        fort and sample some of the best seafood in northern Malaysia,
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1203:        Malaysia’s smallest state, Perlis, also marks a change of
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1206:        the royal town, and Padang Besar, where the Malaysian and Thai rail
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1214:        Malaysia’s tourism promotion. But tourism in the area is centered on
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1269:        Buku Malaysia, is said to have the only village book market in
written_2/travel_guides/berlitz1/WhereToMalaysia.txt:1272:        Malaysia’s less-visited east coast offers the visitor a

```


