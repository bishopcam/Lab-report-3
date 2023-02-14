# Lab Report 3 - Researching Commands 
## Cameron Bishop
---
### My chosen command, Less, for reading and navigating through text

In my research I almost exclusively used this page https://man7.org/linux/man-pages/man1/less.1.html. It was good because of the formatting having a section dedicated specifically to all of the possible options along with the less command.

Less is a bash command that shows the text contents of a file one screen at a time. It loads quickly and has integrated features for allowing the user to navigate forward and backward throughout text. Description created after reading (https://phoenixnap.com/kb/less-command-in-linux)

---

### -U
The first command I found that seemed useful for these type of text files was the -U option, where as stated on the linux manual page, unicode formatting characters are displayed along with the original content of the file.  
To use this command you would type something similar to this:  

<code>less -U travel_guides/berlitz1/WhereToMallorca.txt</code>  
  
Executing this in a bash terminal results in this:
```

^M
  ^M
  ^M
    ^M
      ^M
        Where to go^M
        Whether you’re in Palma, a coastal resort, or an inland^M
        village, you can reach any point on Mallorca in half a day, and Menorca^M
        is even smaller and more concentrated. On both islands, tour companies^M
        offer excursions by road or in combinations with boat trips, to see the^M
        mountain and coastal scenery, famed beaches, spectacular caves, and^M
        various purpose-built attractions. At these sights, though, you’ll^M
        invariably be part of a crowd, especially in high season (which grows^M
        every year). Accommodations are also at a premium from July through^M
        September. Charter flights and package deals (hotel and airfare) become^M
        considerably more economical if you’re willing to visit in the shoulder^M
        or off season.^M
       ...
       ...
       Many More Lines of WhereToMallorca.txt
  
```
This is the text file the path was given to, and then all of the formatting for this text is visible, mostly as ^M  

On another file, using the command <code>less -U travel_guides/berlitz1/Bali-history.txt</code> The less command displays this, once again adding the formatting characters to the content of the file 
```
^M
^M
^M
^M
A Brief History^M
Today’s Indonesians mainly descend from people who came from south China via the Malay peninsula and moved along the island chain to Java, Bali, Lombok, and beyond, from 3000 to 1000 b.c. Archaeological finds show that there was a flourishing Bronze Age culture in Bali and Lombok between about 1000 and 100 b.c. Trade and cultural exchanges with Southeast Asia had certainly begun by that period, and there were frequent contacts with India by a.d. 100. About this time, too, wet rice cultivation was introduced to Bali, changing the face of the countryside to its present appearance of rice paddy fields and terraces.^M
...
...
Many More Lines of Bali-history.txt

```
The differences between these files highlights the usefulness of this command for more easily distinguishing why these files appear differently, because now it is more obvious where linebreaks from the displaying through less, and the formatting in the text of the writing is, distinguished by these ^M notes.  
  
---
### -N
The second option for less that is nice for these type of text files was the -N option, stated on the linux manual page as simply "Causes a line number to be displayed at the beginning of each line in the display." (Linux Manual)

To use this command you would type something similar to this:  

<code>less -N travel_guides/berlitz1/WhereToMallorca.txt</code>  
  
Executing this in a bash terminal results in this:
```
      1
      2
      3
      4
      5
      6         Where to go
      7         Whether you’re in Palma, a coastal resort, or an inland
      8         village, you can reach any point on Mallorca in half a day, and Menorca
      9         is even smaller and more concentrated. On both islands, tour companies
     10         offer excursions by road or in combinations with boat trips, to see the
     11         mountain and coastal scenery, famed beaches, spectacular caves, and
     12         various purpose-built attractions. At these sights, though, you’ll
     13         invariably be part of a crowd, especially in high season (which grows
     14         every year). Accommodations are also at a premium from July through
     15         September. Charter flights and package deals (hotel and airfare) become
     16         considerably more economical if you’re willing to visit in the shoulder
     17         or off season.
     ...
     ...
     Many More Lines of WhereToMallorca.txt
     
```
This is the text file the path was given to as displayed by less, but with a simple line number on the left of each line.

On another file, using the command <code>less -N travel_guides/berlitz2/California-WhereToGo.txt</code> The less command displays the California where to go file, with a line number on the left before each line. Some lines are numbered the same, assumedly because the less file splits the singular lines from the text into multiple to display properly from the less command.
```

      1
      2
      3
      4
      5 Where to Go
      6 Many Californians would like to divide their state into two new states, Northern and Southern California — corresponding to what they believe to be two distinct frames of mind as represente
      6 d by San Francisco and Los Angeles. In fact you will find a little bit of both — San Francisco’s sophistication and Los Angeles’ sunny craziness — all over the place.
      7 Our journey begins with San Francisco and its nearby attractions and works its way down the coast to Los Angeles and San Diego before heading inland to the mountains and deserts of the Sier      7 ra Nevada and Death Valley. You can turn this itinerary upside down if you prefer, but either way, you should also consider making an excursion to Las Vegas, California’s favorite out-of-st
      7 ate playground.
      8 You can get to almost all these places by train or bus, and air travel is quite cheap. However, the car is king, and it’s difficult to enjoy the full scope of this vast and varied landscape      8  without driving. San Francisco is unusual for California in that it is a walker’s town, with buses and cable cars to help you up and down the hills. Los Angeles is undeniably car country,       8 though it is trying to alleviate its congestion and pollution by building a light-rail network. Out-of-town attractions such as the national parks, and especially Death Valley, are most eas
      8 ily reached by car, although once there it’s more rewarding to leave your vehicle behind and explore on foot.
      9 San Francisco
      ...
      ...
      Many More Lines of California-WhereToGo.txt
```
---
### -p(pattern)
The third option for the less command is one of the more powerful ones I decided to showcase, the -p command, where when you give a pattern to be found in the text, less will start at the first line containing the pattern and when less displays the text it will find all of the instances of this pattern.

To use this command you would type something similar to this, where the pattern Mallorca is what we give as parameter pattern to start the less display on, and highlight:  

<code>less -pMallorca travel_guides/berlitz1/WhereToMallorca.txt</code>    

**NOTE: normally in the terminal, the instances of Mallorca will be highlighted, but formatting is lost in the code block, so I replaced the instances of Mallorca with MALLORCA, so they can still easily be distinguished like the bash output.**
```
 village, you can reach any point on MALLORCA in half a day, and Menorca
        is even smaller and more concentrated. On both islands, tour companies
        offer excursions by road or in combinations with boat trips, to see the
        mountain and coastal scenery, famed beaches, spectacular caves, and
        various purpose-built attractions. At these sights, though, you’ll
        invariably be part of a crowd, especially in high season (which grows
        every year). Accommodations are also at a premium from July through
        September. Charter flights and package deals (hotel and airfare) become
        considerably more economical if you’re willing to visit in the shoulder
        or off season.
        Hiring a car (see page 104) is the ideal way to see MALLORCA
        and Menorca, allowing you to go where you like — some of the
        least-known places are the most delightful. You can get around by
        public bus, with a couple of trains thrown in, but those options won’t
        allow you to see as much in a short time.
        The great majority of visitors enter the Balearics through
        its capital, Palma de MALLORCA (and in fact, most stay within 20 km (13
        miles) or so of the city, ensconced in seaside hotels and villas). Any
        thought you might have had that you would be vacationing in a sleepy
        Mediterranean island backwater will quickly be dashed upon arrival at
        sprawling Son Sant Joan, Palma de MALLORCA’s international airport.
        As islands go, MALLORCA is quite large: it has more than 550
        km (325 miles) of coastline and is, at its widest, 100 km (60 miles)
        across. Visiting all the major regions of MALLORCA with any degree of
        ...
        ...
        Many More Lines of WhereToMallorca.txt
```
To use this command on a different file you would type something similar to this, where we give the pattern Chinese, to start the less display at the first mentioning of Japans neighbor:  

<code>less -pChinese travel_guides/berlitz1/HistoryJapan.txt</code>    

**NOTE: normally in the terminal, the instances of Chinese will be highlighted, but formatting is lost in the code block, so I replaced the instances of Chinese with CHINESE, so they can still easily be distinguished like the bash output.**
```
   third-century CHINESE documents speak of a Japanese priestess-queen,
        Himiko, ruling over a land of law-abiding people who enjoyed alcohol
        and were divided into classes distinguished by tattoo marks. Five
        centuries later, Japan’s own Kojiki and Nihon-shoki chronicles describe
        the creation of the imperial dynasty in the year 660 b.c. : the first
        emperor, Jimmu (“Divine Warrior”) — great grandson of the Sun Goddess’s
        grandson — embarked on an expedition of conquest from Kyushu along the
        Inland Sea coast to the Yamato plain of the Kinki region (near
        modern-day Nara).
```
---

### -X
The Last option for the less command I thought would be interesting to showcase is the -X command which is an interesting command because it does not actually alter what ends up being displayed by the less command, but rather alters the behavior when closing out of the less file view. When -X is used, when the less instance is exited by the user, instead of clearing the screen, the text stays in the bash window.
To use this command you would type something similar to this:  

<code>less -X travel_guides/berlitz1/WhereToMallorca.txt</code>  
  
Executing this in a bash terminal results in this:

**NOTE: I am including entering the bash command to highlight how unlike without the -X modifier, the text stays after the less window is exited**
```
bisho@7B7A78 MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ less -X travel_guides/berlitz1/WhereToMallorca.txt





        Where to go
        Whether you’re in Palma, a coastal resort, or an inland
        village, you can reach any point on Mallorca in half a day, and Menorca
        is even smaller and more concentrated. On both islands, tour companies
        offer excursions by road or in combinations with boat trips, to see the
        mountain and coastal scenery, famed beaches, spectacular caves, and
```
To use this command on a different file it would give a similar result, where the output does not change, but it will stay in the terminal after it is exited. Here is less being used on the IntroEgypt file.

<code>less -X travel_guides/berlitz1/IntroEgypt.txt</code>

```
bisho@7B7A78 MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$ less -X travel_guides/berlitz1/IntroEgypt.txt





        Egypt and
        the Egyptians
        E gypt’s long and illustrious history seems to hold the
        modern world spellbound. The ancient Empire that flourished here from
        2500 b.c. until just before the dawn of Christianity was, arguably, the
        greatest civilization that the world has ever seen. Two hundred years
        ago, after Napoleon sent his army officers to explore the land and
        bring back the first hand-drawn impressions of half-buried statues and
        columns, the world couldn’t get enough. When Howard Carter peered
        through the dusty air of Tutankhamun’s tomb in 1922 and, in his own
        words, “wonderful things” met his eyes, he confirmed the immeasurable
        wealth of the Pharaohs, and when the backer of the dig, Lord Carnarvon,
        died suddenly only a few months later, vox populi blamed it on the
        curse of the Pharaohs mummy — and Hollywood was quick to feed our
        fantasies. Today, “pseudo-scientific” theories about the origin and
        purpose of the pyramids fill the stands of bookshops and the listings
        on documentary channels. Our interest and curiosity about Egypt is, it
        seems, insatiable.
        Due to this unprecedented attention, people travel to Egypt
        with preconceived ideas, in addition to a sense of excitement and
        anticipation. But when it comes to the reality of the archaeological
        sites, nothing prepares you for their beauty, scale, and magnificence.
        The colossal statues are overwhelming, the delicate grace of the tomb
        paintings breathtaking, the pyramids prodigious, and the huge temple
        complexes positively Herculean. One can see how archaeologists arrive
        for one season and never leave — the ruins and artifacts, like the
        enigmatic smile of the Sphinx, pose more questions than we have
        answers.
        There’s no doubt that the mysteries of the ancient are the
        lure that attracts most visitors, yet there is much to be said of
        modern Egypt — the archaeological sites do not sit in a geographical or

bisho@7B7A78 MINGW64 ~/OneDrive/Documents/GitHub/docsearch/written_2 (main)
$
```
As you can see, the behavior is similar, where the text is left after the less window is closed, and the command line opens up to bash commands again.
