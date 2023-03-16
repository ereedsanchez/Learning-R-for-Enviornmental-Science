Lesson 5 - Environmental Data 

Today we will build upon our Global Warming graph. 

You will view the data from the spreadsheet, and add new information to your graph including temp max, and temp min data. We will the new data, and create an average of the annual temp min and temp max. 


To do in graph: 

1. Create variable “yearly_tempmax”, and calculate the average yearly temp max temperatures.   yearly_tempmax <- aggregate(tempmax ~ format(NYCdata$datetime, "%Y"), data = NYCdata, mean) 
2. Add line to graph of the “yearly_tempmax” data.   lines(yearly_tempmax$`format(NYCdata$datetime, "%Y")`, yearly_tempmax$tempmax) 
3. Create variable “yearly_tempmin”, and calculate the average yearly temp min temperatures.  
4. Add line to graph of the “yearly_tempmin” data.  
5. Add color to your lines.    yearly_tempmax <- aggregate(tempmax ~ format(NYCdata$datetime, "%Y"), data = NYCdata, mean, col=“red”)


Answer the following questions 

1. What part of the code creates a variable and stores the data from the csv? 
2. What does this line of code do?  NYCdata$datetime <- as.Date(NYCdata$datetime) 
3. What part of the code creates a variable “yearly_temperatures” and calculates the average temp for the year? 
4. What do you change from the previous answer (answer to #3), to calculate the average yearly temp max temperatures? 
5. Which line of code adds a linear regression line for yearly_temperatures? 




FINAL CODE

# R! Code. Written by Edwin Reed-Sanchez
# NYC-temp.csv is data from https://www.visualcrossing.com/weather/weather-data-services/New%20York%20City,USA/metric/2023-01-01/2023-03-01
# Average yearly temporatures and graph with best fit line 

# Create a variable and store the data from the CSV file
NYCdata <- read.csv("NYC-temp.csv")
tail(NYCdata)

# Convert the datetime column to the correct format
NYCdata$datetime <- as.Date(NYCdata$datetime)

# Calculate the average yearly maximum temperature
yearly_temperatures <- aggregate(temp ~ format(NYCdata$datetime, "%Y"), data = NYCdata, mean)

yearly_tempmax <- aggregate(tempmax ~ format(NYCdata$datetime, "%Y"), data = NYCdata, mean)

yearly_tempmin <- aggregate(tempmin ~ format(NYCdata$datetime, "%Y"), data = NYCdata, mean)

# Create a line plot of the average yearly maximum temperature
plot(yearly_temperatures$`format(NYCdata$datetime, "%Y")`, yearly_temperatures$temp, type = "l", ylim=c(0,20), xlab = "Year", ylab = "Average Temperature")

lines(yearly_tempmax$`format(NYCdata$datetime, "%Y")`, yearly_tempmax$tempmax, col = "red")

lines(yearly_tempmin$`format(NYCdata$datetime, "%Y")`, yearly_tempmin$tempmin, col = "blue")

# Add a linear regression line
abline(lm(yearly_temperatures$temp ~ as.numeric(yearly_temperatures$`format(NYCdata$datetime, "%Y")`)))

## abline(lm(yearly_tempmax$tempmax ~ as.numeric(yearly_tempmax$`format(NYCdata$datetime, "%Y")`)))

title(main="Global Warming in NYC", sub="")
   #xlab="x-axis label", ylab="y-axis label")

legend("bottomright", inset=.05, title="Average Temps",
   c("Temp Max","Temp","Temp Min"), fill=c("red", "black", "blue"))
