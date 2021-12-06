---
title: 'Basic stats'
date: 2019-02-11T19:27:37+10:00
draft: false
weight: 2
---

The network has been created by looking at every character page and seeing which character that character links to. From this a netwhork has been created and we will look at the GCC for this network, both the directed and the undirected. 

## Undirected GCC
Starting by looking at the table below. The network has 1551 nodes and 5652 edges. The average degrre is 7.3 and average distance between 2 nodes are 3.7. 


| Description | Value |
| ----------- | ----------- |
| Number of nodes | 1551       |
| Number of edges  | 5652       |
| Average degree  | 7.3      |
| Average distance between 2 nodes  | 3.7      |

Looking at the most connected nodes in the graph:
1. Eric Cartman:    522 edges
2. Stan Marsh:      348 edges
3. Kyle Broflovski: 298 edges
4. Butters Stotch:  239 edges
5. Randy Marsh:     233 edges

When looking at the 5 most connected characters then it is interesting that Kenny McCormick is not one of them, since he is one of the 4 main characters of the show. An explanation to this could be that he never really talks in the show, but he mumbles through everything and it can therefore be hard to understand the character. Butters and Randy are highly connected since they are a big part of the show.

### Degree distribution
Looking at the degree distribution for the undirected GCC. 
!["degree distrubtion undirected gcc"](/images/UGCC-degree-distribution.png)
The degree distrbibution tells us that the network is not random. This is expected since we have some characters that are in every episode of the show and a lot of characters that only show in a single episode or a few. This gives a very uneven distribution through the network. 

### Plotting the network
Below is the undirected gcc plottet using forceatlas2. The nodes are sized after how many degrees it has and the color is chosen from which categroy it belongs to. 
!["undirected gcc"](/images/undirected-gcc.png)

From this it is clear to see that there are a handfull of hubs that almost all other nodes connect to. This is also what we saw when looking at the degree distribution plot, that there were a few characters that had a lot of nodes connected to them. There are also a lot of nodes with only a few edges, which is expected since some characters are only part of 1 or a few episodes. The hubs have the same color, which makes sense since they primarily have the category '4.th grader'.

## Directed GCC
We will now look at the directed GCC. Starting by looking at the table below. As it can be seen then we have 983 more edges in the directed graph. This makes sense since an edge can point both ways between nodes, there fore will avregade degree also be higer. The average distance between nodes are a little smaller, which also makes sense since there are more edges.
| Description | Value |
| ----------- | ----------- |
| Number of nodes | 1551       |
| Number of edges  | 6635       |
| Average degree  | 8.6     |
| Average distance between 2 nodes  | 3.4  

Looking at the most connected nodes in the graph:
<pre>
5 most in degree:                   5 most out degree:
1. Eric Cartman: 509 edges          Eric Cartman: 88 edges
2. Stan Marsh: 341 edges            Heidi Turner: 74 edges
3. Kyle Broflovski: 294 edges       Douchebag: 44 edges
4. Butters Stotch: 230 edges        Stan Marsh: 41 edges
5. Randy Marsh: 222 edges           Randy Marsh: 40 edges
</pre>
 
This shows that there are 996 more edges in the directed graph. Average degree is higher since we can have edges going both ways between nodes. The average distance between 2 nodes are about the same as in the undirected, this is expected.  
The 5 most connected characters in regards to in degree are actually same as in the undirected graph. That is the same characters is somewhat expected since they are main characters in the show. The 5 most connected characters in regard to out degree is a bit more surprising since Heidi turner and douchebag is in the list. Heidi Turner is a main character in the series and is the most popular girl in the 4.th grade, and therefore it makes a bit sense that she has a lot of out degrees. Douchebag or "The new kid" as he is also known by is from the two video games that has been created. It does therefore also make sense that he is a key person in the network.

### Degree distribution
Looking at the degree distribution for in and out degrees.
!["degree distrubtion directed gcc"](/images/DGCC-degree-distribution.png)
As the plot shows then in and out degree do follow each other pretty well. It shows that the hubs or main characters has a lot more in degrees than the rest of the network and lays flat on on the x axis. There is a lot of characters with a single or a few links, which also makes sense since there are characters only showing in a single or a few episodes.

### Plotting the network
Below is the Directed gcc plottet using forceatlas2. The nodes are sized after how many degrees it has and the color is chosen from which categroy it belongs to. The edge color is chosen from which node it is pointing to's category. 
!["Directed gcc"](/images/directed-gcc.png)
The plot is very similiar to the undirected one. As it can be seen then most of the edges has the same color, this is because they are pointing the a node with the category '4.th grader'. This is the category for most of the main characters.