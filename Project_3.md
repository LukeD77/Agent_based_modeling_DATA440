# Project 3 - Final Project

We started off following the guide “Dr Ds Idiots Guide to Spatial Interaction Modelling for Dummies - Part 1: The Unconstrained (Total Constrained) Model” at the following link: https://rpubs.com/adam_dennett/257231. Following the guide, we created a gravity model for London using data gathered from the UK government office of national statistics for the polygons of the United Kingdom, which we then filtered down to just London. We then wanted to calculate distance, but had to change from lat/long distances to meters using spTransform and spDists. We then gathered commuting data from the 2001 England and Wales Census. In the census, Englanders were asked their home address, location of workplace, and how they get there. According to Garcia et al. (2015), migration data can be collected in many other ways, such as GPS, cell phone, transportation networks, or national surveys. These datasets are not as prevalent in less affluent countries. Another important data asset is census microdata, which allows for greater prediction in gravity modeling. In the idiot's guide, income was also included in modeling migration.

Next, we calculated flows between different boroughs and excluded inter-borough travel. Afterwards, we defined the multiplicative gravity model, the equation of which is shown below.

![equation](https://user-images.githubusercontent.com/67921793/99484664-e0b31800-292e-11eb-8825-c4ff547ff405.png)

After running a Poisson regression to optimize the 4 parameters of the model, the R2 of the model was 0.67. After this guide, I moved to calculate a gravity model for Gambia across all adm1 boundaries.

I started with data collected from worldpop.org and chose the 2010 version of the 5 year internal migration flows for Gambia. Next, I created an origin-destination matrix which contained the number of people migrating from one adm to another, which is shown below. 

Table 1: Origin-Destination matrix. This table contains the number of people migrating from one administrative division to the other. Null values are across the main diagonal because inter-migration within one administrative division was excluded. The divisions are as follows: Banjul, Lower River, McCarthy Island, North Bank, Upper River, Western.
![od values](https://user-images.githubusercontent.com/67921793/99484791-2839a400-292f-11eb-931f-18097916f717.png)

Next, I plotted the migration flows to produce this figure. Clearly, the largest portions of migration are occurring at the Western end of the country, which is also the most heavily populated. 

![migration](https://user-images.githubusercontent.com/67921793/99484862-430c1880-292f-11eb-9cdb-25ceb5db1c89.png)

From there I transformed the lat/long distances into meters and produced a matrix to feed into the gravity model. When using the ddm, I got an adjusted R2 value of 0.8057, which is quite strong. To strengthen the model, I included the variable of the number of nighttime lights and reran the code. Below is the full output of the OD data frame.
![od data frame](https://user-images.githubusercontent.com/67921793/99484958-6c2ca900-292f-11eb-8170-2e9fea935588.png)
The ID FR corresponds to the originating adm and the ID TO corresponds to the arriving adm. The latitude and longitude to and from the adms were converted to a distance in meters which is represented by column “Distance”. “People Count” is the number of people migrating. 

Next, I produced an animation of migration across Gambia. The OD matrix can be used to quantify the number of agents moving to each adm within the model. The gravity model could be used along with the simulation to explain the movement of the agents within the model. This time is on a scale of 5 years, with 25 frames each frame is 73 days. The gravity model could only use the agents in the animation that are explained by the model. In the case of my model for Gambia, it would be roughly 80%.

![output](https://user-images.githubusercontent.com/67921793/99485063-af871780-292f-11eb-9420-001461ec9b2d.gif)

My higher resolution contained an evaluation of the defacto settlement boundaries of 2 adm2s, Kombo South and Kombo Central. I would gather census data from these two areas and designate the location of each individual to a specific defacto settlement. I would then determine their movement over a 5-year period to either another defacto boundary or outside of the areas I am examining. The latitude and longitude for each settlement would be calculated off the center point in order to get an accurate measure of distance once the lat/long is transformed to meters. That way, the number of people and distance can be examined. I would also include other factors such as different types of amenities such as hospitals, schools, or clinics in the areas to determine what effect they have on migration. These data can be overlaid as a raster layer and would have to have their positions extrapolated and integrated into the census data frame in order to be modeled.  

The number of points from each origin would be a log of the people count variable, similar to the one I used when examining the entire country of Gambia, if there are too many people moving to discern. If that is not the case, the number of each migration path would be diluted by taking a certain percentile that grants the smoothest display. The time could be moved so that each frame represents one month of the 5-year census data gathered before. The gravity model, like before, could be used to only model the percentage of agents whose migration is explained by the model, in accordance to the adjusted R2 value. The roads through each adm that we plotted in project 2 can be used as paths for the agents in the animation. This would potentially change the distance between migration points and the time the agents take to migrate. By the way, just wanted to let you know that Caroline F. and I are dating and we met in your machine learning class over the summer!









