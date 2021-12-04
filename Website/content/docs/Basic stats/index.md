---
title: 'Basic stats'
date: 2019-02-11T19:27:37+10:00
draft: false
weight: 3
---

```py
def printBasicStats(G):
    print("Basic stats for the gcc network:")
    N = len(G.nodes())
    K = sum(dict(G.degree()).values())/N
    d = log(N)/log(K)
    print("Number of nodes: ", N)
    print("Number of edges: ", len(G.edges()))
    print("Average degree: ", K)
    print("Average distance between 2 nodes: ", d)
    print("\n5 most connected characters: " )
    degree_list = sorted(G.degree, key=lambda x: x[1], reverse=True)
    for node, degree in degree_list[0:5]:
        print(f'{node}: {degree} edges')
printBasicStats(G)
```
Basic stats for the gcc network:

Number of nodes:  1708

Number of edges:  6788

Average degree:  7.948477751756441

Average distance between 2 nodes:  3.5905203239843737

5 most connected characters: 

Eric Cartman: 568 edges

Stan Marsh: 382 edges

Kyle Broflovski: 325 edges

Butters Stotch: 265 edges

Randy Marsh: 257 edges

We want to show the degree distribution of the network.

![GCC](/GCC.png)
<div align="center">
<iframe src="bokeh.html" width=1000px height=1000px></iframe>
</div>