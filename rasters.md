# Extracting Populations from a Raster and Aggregating to each Unit

## Initial stacking of the raster
Below is my first attempt at stacking the population raster over administrative boundary layer 1 of Gambia. I chose Gambia because it is a smaller country and therefore is easier
to work with.

![First raster stack](https://user-images.githubusercontent.com/67921793/91455531-30aea100-e850-11ea-825c-e50e20ff087c.png)


## End product
Below is the product of stacking the raster over all administrative 1 boundaries.

![Full raster stack for adm1](https://user-images.githubusercontent.com/67921793/91455976-be8a8c00-e850-11ea-921a-2238effa3228.png)

The densest part of Gambia is Western, as illustrated by the figure, while the least dense area is the Lower River.


## Stretch Goal 1
After producing the raster plot with administrative 1 boundaires, I set out to do the same methods but apply it to the second administrative boundary layer. Below is the output.

![Full raster stack for adm2](https://user-images.githubusercontent.com/67921793/91456388-31940280-e851-11ea-841a-da9c7d19e2fc.png)

This figure provides much more clarity to population densities compared to the previous one where we only examined adm1. In congruence with the previous figure, the west bank of Gambia
is highly populated; however, we also densly populated portion in the east, specifically Fukada East. The population is set to a log scale to simply math and reduce large numbers.


## Stretch Goal 2
In the stretch goal, we overlayed adm 1 to the previous plot to display those districts and we included a midpoint value and color for our heatmap.

![Full raster stack for adm1 and adm2](https://user-images.githubusercontent.com/67921793/91456836-bb43d000-e851-11ea-8d65-ed8e9416f803.png)


## Stretch Goal 3
In this stretch goal, we created a 3D model of our raster.

![3D model of full raster stack for adm1 and adm2](https://user-images.githubusercontent.com/67921793/91457192-15dd2c00-e852-11ea-8be5-606c11c21560.png)

Unfortunately I could not figure out how to import the interactive 3D plot, so here are some snapshots of it.

