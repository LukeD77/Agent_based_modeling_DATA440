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

At this point I started to run into issues with the mapping of the final deliverable with distinguished urban areas and population desities. I decided to switch to a different district and restart the process in order to get around my problems. I selected the district Kombo South and produced the following graphs.



![Kombo South Urbanized Areas with Population Densities](https://user-images.githubusercontent.com/67921793/93034473-22aa9f80-f608-11ea-8914-4a03f7718c0c.png)
























































