# Project 2
## Producing a synthetic population of Basse, Gambia

The data for this project were pulled from the 2013 Gambia Demographic and Health Survey, conducted by the Gambia Bureau of Statistics and ICF International. A total of 6,217 houses were visited for the survey. When expanded to persons, 52,691 persons were surveyed out of the total population of 1.9 million people. I created a synthetic population including the variables age, gender, household size, and electricity. The synthetic population was analyzed by the accuracy of determining if the household had electricity, the results of which are discussed later in the writeup. According to the 2013 Gambia Demographic and Health Survey, 45% of households were able to access electricity. There was a sizable difference between demographics with 66% of urban households having electricity compared to 13% of rural households.

First, I plotted the households along the entire adm_0 by creating a PPP object using the rpoint() function. The area of Brikama, Kanifing, and Banjul are the most densely populated areas, and appear as a darker black on the southwestern part of the country. 


![Gambia Households](https://user-images.githubusercontent.com/67921793/97095014-5ece1880-1628-11eb-9c3b-a4b9e085c25d.png)


Afterwards, I generated households using a sampling of the surveyed household to expand the dataset to 276,461 households, which was the total population of gambia dvided by the mean household size which was 8.2. I then generated a PPP object for the syntethic population which is shown below. 

![Gambia Households PPP](https://user-images.githubusercontent.com/67921793/97095030-7ad1ba00-1628-11eb-92e6-ee5f12f4c9a3.png)


As you can see, the population continues to be densest in the Southwest. However, there are many background points found in sparse areas that may be attributed to noise in the data amplified by the bootstrapping I used to broaden the dataset. 
After this I moved to produce a synthetic population of Basse, which is the easternmost region of Gambia. After sampling the households surveyed in Basse to a total of the population divided by the average household size, I compared the density and size of the Basse population surveyed to the national population. 


![Gambia and Basse households](https://user-images.githubusercontent.com/67921793/97095044-a0f75a00-1628-11eb-9bbb-f6ad268447a1.png)


This figure illustrates a comparison between the national household demographics of Gambia (yellow) and the demographics of households in Basse (green). There is a noticeable skew in the data for Basse, and upon digging I found a max size of 95 in a household and numerous other households with extreme values. Below is the same graph but comparing the sampled population from Basse from a sampled population of Gambia entirely. 


![Sampled Gambia and Sampled Basse households](https://user-images.githubusercontent.com/67921793/97095056-c4baa000-1628-11eb-9bd4-e18624efc2ca.png)


Compared to the previous graph, this graph displays less homogeneity, which is typical when sampling from a population with outliers. Even still, the population from Basse displays the same skew. Unfortunatly, when calculating the weighted error, the number of observations minus the weights and divided by the observations again equals 1. This means the sampled dataset is not an accurate representaiton of the actual population. Because the surveyed popluation of Basse was already skewed from the population of Gambia, in order to better equate the sampled Basse population to the population on Gambia the outliers would have to be removed. Due to a smaller sample size, the outliers have a larger influence on the distribution that when bootstrapped only exascerbates the effect. 
When comparing variable combinations used to predict access to elextricity, I plotted heatmaps to illustrate their informative contribution. Most displayed no contribution of the variables, even with different transformations. Below is a heatmap with no augmentations applied ot the data. 


![Heatmap raw](https://user-images.githubusercontent.com/67921793/97095078-0b0fff00-1629-11eb-9794-beb45c2cc757.png)


The columns are age, size, gender, and electricity. Many combinations of age and household size were present in the data, as seen by the green coloration in the age column. However, there were not many combinations found in all four variables that was repeated. Below is a graph augmented by taking the percentile of these combinations, which yielded the best results. 


![heatmap as percentages](https://user-images.githubusercontent.com/67921793/97095091-3e528e00-1629-11eb-8ba0-24c886440129.png)


The columns are age, electricity, gender, and size. Compared the to previous figure, this heatmap display much more heterogeneity and depicts numerous combinations leading to the prediction of electricity.
After this analysis, I performed a multinomial regression and random forest with the sample Basse data to predict whether a household has electricity based upon their household size, gender of occupants, and age of occupants. The multinomial regression had an accuracy of 66.5% while the random forest had an accuract of 67.4%. Considered accessiblity to electricity was a binary variable, so the mean score of prediciton would be 50% without any informative variables, the models were not particularly accurate. A more informative variable would be if the household was in a rural or urban setting. As stated above, there was a large disparity between the availablility of electrivity in households between these two settings with urban areas having a much larger rate of occurance. The ROC curve illustatrates the lack of information the variabels contributed to the prediciton of access to electricity. 


![ROC curve](https://user-images.githubusercontent.com/67921793/97095102-575b3f00-1629-11eb-9405-3550d8980a20.png)

If the variables contributed to the prediction of electricity, the line would be parallel to the x-axis and very low on the y until the end of the graph where it would rise rapidly. Instead, we see a gentle slope. 


























