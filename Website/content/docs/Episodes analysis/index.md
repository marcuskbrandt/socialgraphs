---
title: 'Episode analysis'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 4
summary: Syntax highlighting and menus can be configured via `config.toml`.
---

The tv show has run for many years and therefore is an interesting thing to try to find some insights which we can reach from episodes’ data. On the South Park wiki page we can find a section called “Episodes”, which contains information about all episodes (seasons and special episodes). In this case we will take a look only on episodes from regular seasons, since it allows us to compare how South Park has changed over the years. 

First we decided to investigate relations between characters in the episodes. For this purpose we created a graph of characters in the episodes, characters are linked to each other if they appear in the same episode. The basic stats for the network can be seen below. 

| Description | Value |
| ----------- | ----------- |
| Number of nodes | 1169       |
| Number of edges  | 22432       |
| Average degree  | 38.4    |
| Average distance between 2 nodes  | 2    |

Looking at the most connected nodes in the graph:
1. Eric Cartman:    1168  edges
2. Kenny McCormick: 1168 edges
3. Stan Marsh: 1133 edges
4. Kyle Broflovski: 1130 edges
5. Butters Stotch: 857 edges

When we compare the number of nodes in this network to the number of nodes in the network created form the character pages in the wiki, it can be noticed that there are less nodes. This difference is due to the fact that not all characters mentioned on characters wiki fandom page took part in episodes from regular seasons. Some of them are characters from movies, games or special episodes.
When it comes to the number of edges there are many more in comparison to previous networks. 

When looking at the 5 most connected characters, we have 4 main South Park characters in 4 first places. 5th the most connected character is Butters Stotch who is considered to be one of the major characters too. Based on results we can assume that this is due to the fact how often he appears in episodes.

Looking at the degree distribution:
!["Episodes-degree-distribution"](/images/episodes_degree_dist.png#center)	
The degree distribution tells us that the network is not random. This is expected since we have some characters that appear in most of the episodes and a lot of characters that only show in a single episode or a few. This gives a very uneven distribution through the network. In the network there are no nodes with degree equal to 0 because during all seasons there was no episode in which only one character appeared. 

Now the network can be visulized:


!["Episodes-network"](/images/episodes_network.png#center)	


It is easy to notice a few hubs to which most of the other nodes are linked. Those hubs correspond to major characters of the series and they were also visible on degree distribution plots. Most of the hubs belong to the '4.th grader' category.

### Sentiment analysis through time
South Park as a series is well known from its vulgar language, black humor and touching controversial topics. That was a motivation to take a look at sentiment of its scripts and how sentiment of the series changed over years. Sentiment analysis was performed using VADER, VADER returns a score for a particular text in the form with scores for `compound`, `positive`, `neutral` and `negative`.

To see how sentiment of South Park changed over years we grouped all dialogues and their sentiment score by seasons and computed average compound sentiment score for each season. Results are present in the barplot below.

!["season-sentiment-bar"](/images/season-sentiment-bar.png#center)	
We can see an upward and downward trend of average sentiment over seasons. However, looking at the result, we might be surprised. Most people would expect mostly negative sentiment, where on our result we can see that average sentiment for seasons are neutral (compound score > -0.05 and compound score < 0.05) or positive (compound score >= 0.05). Because of this, we decided to check how the distribution of the compound scores look:

!["episode-compoundt-dist"](/images/episode-compoundt-dist.png#center)	


The results obtained show that just because we view South Park as negative does not mean that it will be classified in the same way. We have to remember that VADER and other sentiment classification are not perfect and can only determine the approximate value of the sentiment contained in the text. They are not always as able to determine the context of a statement or sarcasm as a human. Therefore, sometimes a text which is negative for a person will be evaluated as neutral or positive.

### Sentiment analysis through time - Main characters
After general episodes we decided to focus on 4 main characters and check how their sentiments evolve over time. The 4 main characters have very different personalities which is also something that we hope will be shown in the sentiment analysis. The focus will be on their dialog from the episodes. From data with episode scripts and sentiment scores for each dialogue we filtered out those dialogues which belong to 4 main characters. 

!["episode-compound-main-char"](/images/episode-compound-main-char.png#center)	
As it can be seen the sentiment compound score almost evolves like a sinus curve. It is interesting to look at cartman, since he will be seen by many to very rude to other people. It is then interesting to see that he has a rather positive sentiment in many of the seasons. Even though Kenny doesn't say much (in fact he says normal things in an unintelligible way) he is one of the most emotionally powerful characters. This probably reflects that he is not the happiest guy in the show and comes from a less wealthy family and is always moped by the other characters. Kyle is mostly negative, but has some seasons where he is positive. Stan sentiment is neutral/positive through most of the seasons.
