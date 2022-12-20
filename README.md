# Learning R fro Enviornmental Science @ Belmont

Hello, I am Edwin Reed-Sanchez and I love to program, hack and tinker with technology. I also enjoy teaching students the basic programming principals that are universal with all programming languages.  

For this class we will be learning R, which is a widely programming language used for statistical and scientific analysis.  

## Information about R
- [R](https://www.r-project.org/)
- [R-studio](https://posit.co/downloads/)

## Software for Class
Sign up for [Replit](https://replit.com/) using your gmail account. 
- Email me  at ereedsanchez@gmail.com with me your username. 
- My replit uysername is: [replit.com/@ereedsanchez](https://replit.com/@ereedsanchez)

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



## Lesson 3 | Wolves and Moose Data 

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

## Lesson 1 - The Basics
Today we will learn about basic programs and syntax used in R. 

### Print
`print(“text”)`

### Commenting
`#Comments your code`

### Variables using =
```R
x = 51
print(x)
```
```R
name = “sam”
print(sam)
```


### Variables using <-
### leftward <- operator

```R
X <- 42
print(X);
```
```R
x <- 9
y <- 3 
x <- y 
print(x)
```

### Data Types - Numbers
```R
#numeric
var1 <- 3.14

#integer
var2 <- 88L

print(var1)
print(var2)
```

### Data Types - Strings - Simple Text

```R
#text
var3 <- "hello"
print(var3)
```




### Data Types - Strings - quotations 

```R
message <- "This is called \"escaping\"."
print(message) 
```
will return
```
[1] "This is called \"escaping\"."
```
—
```R
message <- "This is called \"escaping\"."
cat(message)
```
will return
```
[1] "This is called "escaping".
```


## Lesson 2 - Basic Math

##### Arithmetic 
```R
x <- 11
y <- 4

#addition
print(x+y)

#substraction
print(x-y)

#multiplication
print(x*y)

#division
print(x/y)
```

##### Arithmetic Operators
```R
x <- 11
y <- 4

#exponentation
print(x^y) #or x**y

#modulus (remainder from division)
print(x%%y)

#integer division
print(x%/%y)
```


### Resources 
[Producing Simple Graphs with R](https://sites.harding.edu/fmccown/r/)

[Simple Bar Graphs in R](https://medium.com/beginner-at-bi-data-science-and-big-data/importing-data-into-r-from-a-csv-file-and-creating-a-chart-out-of-it-892d5bc81531_)



