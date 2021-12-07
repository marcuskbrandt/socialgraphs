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