# Project 1
## Part 1
## Deliverable 1
Below is my deliverable 1, which consists of a spatial plot of Gambia depicting a population heatmap and labels of population
density underneath county names. It also shows a barplot of the populations of all the counties in Ghambia, sorted highest
to lowest, as well as the percent of the total population that each county contains. 

![Gambia Deliverable 1](https://user-images.githubusercontent.com/67921793/91791263-add76e80-ebe0-11ea-9504-e01781e07ce4.png)

I created the spatial plot by reusing my Gambia administrative 1 layer and inserted a geom_sf_text layer that contained the density
values we created earlier in the script by dividing the pop19 by the area, which we calculated using st_area.
I created the barplot by plotting the county names and populations, but added extra information by including the percent of
total populations by taking the percent of the pop value divided by the total pop value.
Not many modifications were made from the provided code except the addition of figure titles using ggtitle and slight
adjustments to the label locations. 


## Stretch goal 1
Below is my output for stretch goal 1. I created a bar plot that has sub groups in each column based upon the second layer of
administrative boundaries. I also included a spatial plot of Gambia, which is crowded by labels. I tried to resolve the issue
using this line of code, but I would have the labels all randomly dispersed along coordinates and not specific to the correct
geographical location in the raster.

geom_text_repel(data=gambia_adm2, aes(label=NAME_2), color = 'red', size = 2.5)

![Gambia ADM2](https://user-images.githubusercontent.com/67921793/91794982-6655e000-ebea-11ea-9c50-dfd12b19057c.png)

## Stratch goal 2
Below is my output for stretch goal 2, which is a mp4 of a 3D model of the population density of Gambia split among its second
level of administrative districts.

![Gambia Population Density with adm2](https://user-images.githubusercontent.com/67921793/91795590-08c29300-ebec-11ea-94fd-22410ee9d84c.gif)


## De Facto Description of Urban Areas
In this lesson we mapped boundaries by population densities in our selected areas of our country. I decided to use Foni Brefet,
Gambia at first because it was scarecely populated and therefore easy to compute the boundaries. Below is the point pattern for 
Foni Brefet.

![Foni Brefet ppp Object](https://user-images.githubusercontent.com/67921793/93034138-0ce8aa80-f607-11ea-996d-c4950c75335f.png)

The highest populations appear as a band across the center of the district. This pattern is also evident in the density image
below.

![Foni Brefet Density Image](https://user-images.githubusercontent.com/67921793/93034219-5d600800-f607-11ea-8a95-4f1fa8b14bf9.png)

The contour lines denote thresholds for population densities, with brighter colors within representing higher densities. There are also smaller setllements dispersed through the disctrict, but in congruince with the ppp object the highest population densities are found in a band across the center.

At this point I started to run into issues with the mapping of the final deliverable with distinguished urban areas and population desities. I decided to switch to a different district and restart the process in order to get around my problems. I selected the district Kombo South and then after testing in later parts of the project (identifying roads and health centers), I decided to also add Kombo Central. Below are my graphs for the two districts.

![Kombo South & Kombo Central Raster](https://user-images.githubusercontent.com/67921793/93034794-44585680-f609-11ea-88af-823eb0c03fab.png)

![Kombo South & Kombo Central Density Image](https://user-images.githubusercontent.com/67921793/93034843-7073d780-f609-11ea-8757-c5b5690c5fa0.png)

![Kombo South & Kombo Central Urbanized Areas with Population Densities](https://user-images.githubusercontent.com/67921793/93034954-b6c93680-f609-11ea-8777-15d604918534.png)

This last figure depicts the urban centers of Kombo South and Kombo Central in green and non-urban areas in red. Sorry if you are red/green colorblind. I also included dots representing certain population sizes with colors corrosponding to the popualation densities. The urban centers were hard to tease out with numerous filtering iterations to isolate the main urban centers versus the entire districts. 

In the end, the urbanized plot contained 13 different urban areas ranging from a density of 464 persons per square km to 1584 persons per square km. The range for the areas of each urban center was large with the minimum being 0.0308 and the highest value being 97.5861. The pop also exhibited a large range of 27 to 154368. 

Below is an analysis of whether the population densities follow Zip's Law.
![zips law](https://user-images.githubusercontent.com/67921793/93415595-e24e5a00-f871-11ea-8e34-dd7d8dd98a05.png)

The graph illustrates a deviation from Zip's law, as the log of the densities are not in line with the expected densities. 
The data show a shallower trend than the steeper expected values, meaning that these urban centers are more densly populated
than expected.


## Project 1 pt 2 - Roads and Health Centers
This part of the project consisted of graphing the primary and secondary roads of the selected districts as well as the different health cetners. Below is my final output.

![Kombo South & Kombo Central Urban Overlay with Roads and Health Centers](https://user-images.githubusercontent.com/67921793/93415949-abc50f00-f872-11ea-8659-9b2ec31ece84.png)

The primary roads are marked in red and the secondary roads are marked in pink. The primary roads lead into the populous of Kombo Central, while the secondary roads are used for traversing through the populated areas of Kombo South. I decided to make the points denoting health centers descriptive of their type. H stands for hospital, C stands for clinic, and O stands for other. The health centers are quite dispersed, but are located in densly populated areas and alongside roads. The three health centers marked as other were all pharmacies, which is odd because according to the depicition of just these two counties, the most densly populated area (center of Kombo Central) does not have either a clinic or a hospital. A person living in Kombo Central would need to take one primary road in order to reach a singular secondary road that leads to the closest hospital, which is in the southern most part of Kombo South. There are also no dentist offices in either of these counties. This could lead to inadequate dental care within the regions. 

It is interesting that there is nearly no primary roads in the Kombo South district. A next step would be to include more districts in this graph and see where the roads continue to go, especially once they read the Gambia River. There may be free roads over the river, so urban development near those areas would be important to examine.


## Project 1 pt 3 - Topography
Below is my deliverable for the topographic map of Gambia with an overlay of the urban boundaries produced in part 1 of the project. Unfortunately, the country is quite small and the districts are even smaller, so the urban boundaries are hard to see in the top right corner of the image. Also, the Gambia River flows through the center of Gambia, but the water did not render. The length of the river is still discernable within the topography, but the blue would have been nice to see.

![Gambia Topography](https://user-images.githubusercontent.com/67921793/93041328-3e1ea600-f61a-11ea-9040-cc36089bfe9c.png)



