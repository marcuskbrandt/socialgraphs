---
title: 'Episode analysis'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 4
summary: Syntax highlighting and menus can be configured via `config.toml`.
---


# Sentiment analysis through time
The tv show has run for many years and therefore an interesting thing to look at is how the sentiment has evolved over the years. The focus will be on the 4 main characters and how their sentimental analysis score evolves through the years. The 4 main characters has very different personalities which is also something that we hope will be shown in the sentiment analysis.

The focus will be on their dialogue from all the epsiodes. A dataset can be created from the scripts of every episode and then take out the text where one of the 4 main characters are talking. This csv file can be found on our github [here](https://github.com/koldbrandt/socialgraphs/blob/main/Character_lines_episodes.csv).  

Vader has been used to do the sentiment analysis. In the plot below the avergae compound score for the season is plottet for each main character. Season 24 are the specials that they have created during the pandemic. 

!["Sentiment through the years"](/images/average-compound-seasons.png)

As it can be seen the sentiment compound score almost evolves like a sinus curve. It is interesting to look at Cartman, since he will be seen by many to very rude to other people. It is then interesting to see that he has a rather positive sentiment in many of the seasons. Eventhough kenny doesn't say much he is still get a negative compound score. This probably reflects that he is not the happiest guy in the show and comes from a less wealthy family and are always moped by the other characters. Stan is clearly the most happy person in the group, which is also expected. Kyle is mostly negative, but has some seasons where he is positive.  
Vader do not understand sarcasm, which is a big part of the show. This can also have influenced the score.