# Project 1
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

![Gambia ADM2](https://user-images.githubusercontent.com/67921793/91794811-fa737780-ebe9-11ea-9965-014ce72a34b9.png)
