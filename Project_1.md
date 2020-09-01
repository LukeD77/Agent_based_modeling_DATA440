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
