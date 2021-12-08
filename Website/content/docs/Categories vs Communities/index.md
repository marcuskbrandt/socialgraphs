---
title: 'Communities and Categories'
date: 2019-02-11T19:27:37+10:00
weight: 5
---
To analyse the dataset we will first look into the categories and communities of the dataset. The categories is defined by the wikipage and can be seen in the picture below.

!["Wiki categories"](/images/wikiCategories.PNG#center)	

The category for each character is listed in the bottom of the character page. The pattern for categries are `[[Category: category name]]` like the list below. (the example below is from the character page George W Bush)
<pre>
[[Category:Characters]]
[[Category:Political celebrities]]
[[Category:Presidents of the United States]]
[[Category:Male characters]]
[[Category:Adult characters]]
[[Category:Minor characters]]
[[Category:Characters voiced by Matt Stone]]
[[Category:Characters voiced by Kyle McCulloch]]
[[Category:Elderly people]]
</pre>

<br>

Many of the character pages had the same categories such as "Category:Characters voiced by Kyle McCulloch" and this does not make sense to analyse upon, as almost all characters are voiced by the same actors.
Therefor we decided to filter out all categories that are not one of the categories listed in the picture above. The category "School Characters" and "Creatures" were not referenced on a single page, but "Celebrities" was. 
The idea was to have each character be listed under their subcategory, but as many characters in the celebrity category didn't have a sub category, this idea was dismissed. 

<br>

Many of the characters did not have one of the categories listed above, so instead they were assigned as "uncategorized". This means that the largest category group is uncategorized and the plot below shows the distribution.
	
!["Categories distribution"](/images/categories.png)	

From the above plot, it is clearly visible that half the characters have the "uncategorized" category, and that the largest of the real categories are the celebrities and the 4th graders. 
This is expected, as the show have used alot of celebrities throughout the seasons, and the 4th graders are the main characters of the show. 

<br>

The communitys are found using the louvain algorithm. The modularity of the network is found to be 0.442. 
As the modularity is positive, the number of edges within each community are greater than the number of edges would be if the communities were picked at random. 
The number also suggest that each character within the communities are connected to alot of other characters. 
Furthermore, the modularity is considered an optimal modularity (Network science, image 9.16). This means that the algorithm has correctly identified each community and their members.

<br>

The plot below shows the gcc network with each node colored corresponding to the community. The plot can be compared to the gcc plot where each node is colored corresponding to their category. 
The number of characters in each community can also be seen, it is however not easy to distinguish, as some of the nodes are very small.
Therefor a bar plot with each community size, named after their most connected character, will also be created.


!["Community Network"](/images/gcc-community.png)

The number of characters in each community can also be seen on the above plot, it is however not easy to distinguish, as some of the nodes are very small.
Therefor a bar plot with each community size, named after their most connected character, can be seen below.

!["Community distribution"](/images/CommunityBarPlot.png)

From the above plot it is clearly visible that the "Heidi Turner" community is the largest, and that generally the communities are quite large. 
It can also be seen that the four main characters each are the main character of a community, meaning that they are the most connected character within that community. 
We can now investigate which category is the most common within each community.

| Community name  | Category  |
|---|---|
| Heidi Turner  |  uncategorized |
|  Eric Cartman |  uncategorized |
|   Stan Marsh | celebrities  |
|   Kenny McCormick | uncategorized  |
|   Ike Broflovski | uncategorized  |
|   Randy Marsh | uncategorized  |
|   Satan | uncategorized  |
|   Butters Stotch: | uncategorized  |
|   Kyle Broflovski | uncategorized  |
| Herbert Garrison| uncategorized|
| Timmy Burch| uncategorized|
| Officer Barbrady| uncategorized|
| Sharon Marsh| celebrities|
| Muhammad| 4th graders|
| Barack Obama| uncategorized|
| Franz| uncategorized|

Clearly almost every community will have the uncategorized category as their most commmon category. 
This makes sense as uncategorized was by far the largest category, as described at the start of the section. 
The few communities where the most common category is not uncategorized, have the two other largest categories, celebrities and 4th graders. 
The Stan Marsh community has many celebrities, meaning that stan and his community mainly consists of celebrities. 

As the above list does not give a detailed overview of the most common categories, the most common categories are removed in the list below (unless the community only contains characters with one of the major categories)

| Community name  | Category  |
|---|---|
| Heidi Turner| crossover characters|
| Eric Cartman| 4th graders|
| Stan Marsh| political celebrities|
| Kenny McCormick| television celebrities|
| Ike Broflovski| television celebrities|
| Randy Marsh| crossover characters|
| Satan| kindergartners|
| Butters Stotch| 4th graders|
| Kyle Broflovski| music celebrities|
| Herbert Garrison| television celebrities|
|Timmy Burch| animals|
| Officer Barbrady| political celebrities|
| Sharon Marsh| political celebrities|
| Muhammad| 4th graders|
| Barack Obama| uncategorized|
|Franz| television celebrities|

Most of the communities still have celebrities as the most common members, and interesstingly, the four main characters each have a different category within their communities.
It is also worth to note that the main category in the satan community is the kindergarterners (evil little pricks).

To analyse the communities further, the TF and TF-IDF are calculated. Below both results are shown for the five largest communities.
## TF
Community Heidi Turner
: ('randy', 0.0158), ('black', 0.0109), ('character', 0.0097), ('hair', 0.0095), ('brown', 0.0092)

Community Eric Cartman
: ('kenny', 0.0138), ('black', 0.0083), ('cartman', 0.0075), ('hair', 0.0069), ('appearance', 0.0055)

Community Stan Marsh
: ('cartman', 0.0305), ('hair', 0.0079), ('black', 0.0076), ('kyle', 0.0074), ('cartmans', 0.0063)

Community Kenny McCormick
: ('butter', 0.033), ('hair', 0.008), ('character', 0.0079), ('appearance', 0.0074), ('cartman', 0.0065)

Community Ike Broflovski
: ('timmy', 0.0088), ('hair', 0.0078), ('jimbo', 0.0072), ('character', 0.007), ('appearance', 0.0068)

## TF-IDF
Community Heidi Turner
: ('mickey', 0.0044), ('haha', 0.0025), ('marvel', 0.0024), ('pangolin', 0.0023), ('randy', 0.002)

Community Eric Cartman
: ('mysterion', 0.0041), ('stuart', 0.004), ('coon', 0.0034), ('henrietta', 0.0029), ('spielberg', 0.0025)

Community Stan Marsh
: ('hakeem', 0.0015), ('maury', 0.0015), ('camper', 0.0015), ('stuffed', 0.0013), ('liane', 0.0012)

Community Kenny McCormick
: ('linda', 0.0057), ('lemmiwinks', 0.0041), ('charlotte', 0.0041), ('paris', 0.0031), ('stephen', 0.003)

Community Ike Broflovski
: ('nathan', 0.006), ('mimsy', 0.0055), ('scuzzlebutt', 0.0055), ('timmy', 0.0047), ('jimbo', 0.0046)

This gives a nice overview of what terms are most relevant to each community. 

## Wordclouds

Below are the wordclouds for the five largest communities, created by looking at the TF-IDF for each community.

!["Heidi Turner Community"](/images/HeidiTurnerCommunity.png#center)

!["Cartman Community"](/images/EricCartmanCommunity.png#center)

!["Stan Marsh Community"](/images/StanMarshCommunity.png#center)

!["Kenny Community"](/images/KennyMcCormickCommunity.png#center)

!["Ike Broflovski Community"](/images/IkeBroflovskiCommunity.png#center)

For the Cartman community it is clear that he is a main character, and that alot of members in the community probably relates to the main characters. 
This is also confirmed by the previous result of the most common category within the Cartman community, which was 4th graders. 
For all the wordclouds, a reappearing words are "hair" and "black". This might be because the words are used to describe many of the characters.

<br>

We can also analyse the pages by looking at the most used words from the joined text of the pages. This is done by creating a cumulative distribution of the 50 most used words.

!["Cumulative distribution"](/images/wordSum.PNG#center)

Furthermore, we check if Zipf's law is applicable on the dataset. 
Zipf's law states that the most used word is used twice as must as the second most used word, and so forth. 
We compare this with the plot of a random list of words.

!["Zipf's law"](/images/Zipfslaw.png#center)

From the above plots it can be concluded that the southpark text does not follow zipfs law at the start, as it does have a high number of words that are used alot. 
But as the frequency of words lower, zipfs law fits better and better on the dataset. 


