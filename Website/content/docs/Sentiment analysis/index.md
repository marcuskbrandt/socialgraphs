---
title: 'Sentiment analysis'
date: 2019-02-11T19:27:37+10:00
weight: 2
---

To analyse the sentiment of the character pages, both the vader lexicon and the labMT scores are used. The presumption is that the results of the two different methods will differentiate alot. 

The most positive character pages according to the vader compound score:

|Character name  | Vader compound score  |
|---|---|
| Douchebag| 0.9998|
| Jimmy Valmer| 0.9988|
| Timmy Burch| 0.9974|
| Nichole Daniels| 0.9965|
| Seaman| 0.9948|
| Jesus Christ| 0.9943|
| Girl with Blonde Hair| 0.9942|
| Stephen Abootman| 0.9939|
| Maggie Yates| 0.9935|
| Lola | 0.9932|

The most positive character pages according to the vader compound score:

|Character name  | Vader compound score  |
|---|---|
|Herbert Garrison | -0.9996|
|Principal Victoria | -0.9996|
|Nathan | -0.9997|
|Saddam Hussein | -0.9997|
|Stan Marsh | -0.9999|
|Heidi Turner | -0.9999|
|Randy Marsh | -0.9999|
|Butters Stotch | -0.9999|
|Kenny McCormick | -1.0|
|Eric Cartman | -1.0|

Interesstingly, the main characters have the lowest compound score, and are thus the characters described in the most negative way according to vader. 
The happiest guy is douchebag which makes a lot of sense since he is always happy in the episodes, and he is "new" to South park. 

To get a better understanding the Vader scores can be plotted using histograms.

!["Vader Histograms"](/images/vaderHist.png)	

So from the compound plot, it can be seen that most of the characters are described in a very negative way. 
This is especially clear in the last plot, where the compound score clearly shows that almost a third of the pages have a compound score between -1 and -0.75 meaning the wording of the pages are negatively charged. 

Below is the results from the labMT analysis.

The most positive character pages according to the labMT happiness score:

|Character name  | labMT score  |
|---|---|
|Mary, Mother of Jesus | 5.9757|
|Ugly Girl (Probably) | 5.7279|
|Charlotte's Mother | 5.6925|
|Canadian Gift Shop Owner | 5.6331|
|Spinny Mountain Records Producer | 5.633|
|Mr. Allen | 5.4544|
|Girl with Pink Coat | 5.4196|
|Jeffy's Farmer | 5.4034|
|6th Grader Girl with Blonde Hair | 5.3993|
|Vegan Boy | 5.3928|

The most negative character pages according to the labMT happiness score:
|Character name  | labMT score  |
|---|---|
|Feldspar the Thief | 3.1701|
|Vaping Man | 3.1664|
|Marty | 3.1189|
|John Wilkes Booth | 3.0539|
|Predator | 3.0436|
|Clone Stan Marsh | 3.0079|
|Tinkerbell | 3.0029|
|Ranger McFriendly | 2.8883|
|Fifi | 2.8494|
|Rex | 2.2044|


The most positive is Mary, the mother of jesus, which makes good sense since she is considered by millions to be the holiest and greatest saint. 
She also plays a very small part in the series, which is also the case with the rest of the characters. 
All of the characters with the happiest and saddest pages according to labMT has very limited text in their pages, and therefor only a few words is used to calculate the labMT score. 



In conclusion the best analysis of this dataset is carried out by looking at the vader score instead of the labMT score. 
Below the Vader positive result, and the labMT scores are plotted next to each other. 
Interestingly, the labMT actually looks like a normal distribution, whereas the vader is rather right skewed. 
From this we can conclude that vader generally interprets the text in a negative way and that labMT scores the text as almost neutral. 

!["labMT vs Vader Histograms"](/images/labmtvsvader.png)	

The vader analyser is therefor chosen to look at the scores for each of the main characters

|Character name  | Negative score | Neutral score  | Positive score  | Compound score  |
|---|---|---|---|---|
Eric Cartman | 0.213 | 0.638 | 0.148 | -1.0|
Stan Marsh | 0.202 | 0.657 | 0.141 | -0.9999|
Kyle Broflovski | 0.191 | 0.645 | 0.164 | -0.9995 |
Kenny McCormick | 0.201 | 0.663 | 0.136 | -1.0 |

So they all have very negative compound scores. This is not surprising as the following wordclouds will demonstrate

!["Cartman"](/images/EricCartman.png)
!["Stan"](/images/StanMarsh.png)
!["Kyle"](/images/KyleBroflovski.png)
!["Kenny"](/images/KennyMcCormick.png)
