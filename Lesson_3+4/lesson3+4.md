## Lesson 3 | Wolves and Moose Data 

DataSet: https://docs.google.com/spreadsheets/d/12M3CZlN1M3xWpR7FJZ5BURpqs1sxNTtaHzLc_UfKADc/edit#gid=0

#### R! Code 

```
data <- read.csv('IsleData.csv')
print(data)
year <- data[ , c(1)]
wolves <- data[ , c(2)]
moose <- data[ , c(3)]

plot(year, (wolves*20), type="l", col="brown", ylim=c(1,2500))
lines(year, moose, type="l", col="green")
```
----------


## Lesson 4 | Wolves and Moose Data Complex Graphs 

#### Learn


#### Full R! Wolves and Moose Data Code 
```
data <- read.csv('IsleData.csv')
# print(data) # See if data is imported
year <- data[ , c(1)] 
wolves <- data[ , c(2)]
moose <- data[ , c(3)]

# Wolves Graph
par(mar = c(5, 4, 4, 4) + 0.25)
plot(year, wolves, type="l", col="red", axes=FALSE)
axis(2, ylim=c(1,50), col="red",las=1)
axis(1, ylim=c(1980,2020),col="black",las=1)
box()

# Moose Graph
par(new=TRUE, mar = c(5, 4, 4, 4) + 0.25)
plot(year, moose, type="l", col="green", ylab = "", axes=FALSE)
# New axis
axis(4, ylim=c(1,3000), col="green",las=1)
# Axis label
mtext("Moose", side = 4, line = 3, col = "green")

```

#### Understand

##### plot
`plot(year, wolves, type="l", col="red", axes=FALSE)`
`plot(x-axis, y-axis, type="", col="", axes=TRUE/FALSE)`

Plot Documentation 1: https://www.rdocumentation.org/packages/graphics/versions/3.6.2/topics/plot

Plot Documentation 2: https://www.digitalocean.com/community/tutorials/plot-function-in-r

##### type=""
"p" for points,
"l" for lines,
"b" for both,
"c" for the lines part alone of "b",
"o" for both ‘overplotted’,
"h" for ‘histogram’ like (or ‘high-density’) vertical lines,
"s" for stair steps,
"S" for other steps, see ‘Details’ below,
"n" for no plotting.
Plot Documentation 1: https://www.rdocumentation.org/packages/graphics/versions/3.6.2/topics/plot

##### par
R also allows combining multiple graphs into a single image for our viewing convenience using the par() function. We only need to set the space before calling the plot function in our graph.

##### Axis customization 
Axis Documentation: https://r-charts.com/base-r/axes/

----------
