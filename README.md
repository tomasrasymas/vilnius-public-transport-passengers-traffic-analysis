# Vilnius public transport passengers traffic analysis

This analysis is performed on publicly available data https://github.com/vilnius/keleiviu-srautai.git. Data consists of 2016 year passengers flow data (entering bus (IN) and leaving the bus (OUT)). 

## Data preparation 

Cause each month data is stored in different CSV format files, data must be concatenated into single data structure. Each bus can have different number of people counters (depends on bus type) and each counter results are stored into different fields in CSV file. In order to get final numbers those fields values must by summed up. I am using just part of data that is stored in files: Direction, Line, Stop name, Stop number, Passengers In, Passengers Out, Stop longitude, Stop Latitude. Stops coordinates are stored in another file so passengers traffic data and stop data was joined using Stop number field. Data cleaning was performed in order to remove abnormal values. Few example of abnormal values: passengers entered bus on single stop is negative (-999996) or really to high (1231) same with passengers leaving the bus. All abnormal data was removed leaving passengers in/out numbers between 0 and 20.

## Passengers flow per month

First of all I am interesting to see the overall passengers flow per month. 

![alt text](docs/passengers%20per%20month.png "passengers per month bar")

Usage of Vilnius public transport rises till May, then it starts to decrease and after the summer, from August it starts to increase again. Number of passengers entering and leaving the bus are different, it shows that automatic passengers counters that are used in buses are not accurate.

## Passengers flow heatmaps

In order to view how passengers are moving in the city I created passengers IN and passengers OUT heatmaps, that shows number of passengers in each stop.  
URLs:
* [Passengers IN](https://cdn.rawgit.com/tomasrasymas/vilnius-public-transport-passengers-traffic-analysis/master/docs/in_heatmap.html)
* [Passengers OUT](https://cdn.rawgit.com/tomasrasymas/vilnius-public-transport-passengers-traffic-analysis/master/docs/out_heatmap.html)

![alt text](docs/heatmap%20passengers%20in.png "passengers in heatmap")

![alt text](docs/heatmap%20passengers%20out.png "passengers out heatmap")

Main courses: Žirmūnai, Ladynai, Baltupiai, Santariškės, Šnipiškės and Savanorių pr. What is more we can see ow different seasons and trips changes influences passengers traffic course. Main (hottest) areas for passengers entering the bus and leaving are almost the same.

## Routes analysis

Which routes are most popular in Vilnius?

![alt text](docs/popular%20routes%20passengers%20in.png "popular routes passengers in")

![alt text](docs/popular%20routes%20passengers%20out.png "popular routes passengers out")


Directions ATEITIES G.-BUKCIAI, BUKCIAI-ATEITIES G, FABIJONISKES-MARKUCI, MARKUCIAI-FABIJONISK are popular all year, other directions load depends on season and other factors. What is more, popular directions for IN/OUT are the same. Almost all directions to/from depot are "unpopular" with least passengers. 

## Passenger flow by week day

It is interesting to inspect passengers traffic flow by week days over year and single month. At this point I am analyzing only count of passengers IN value.

![alt text](docs/Passengers%20flow%20by%20week%20per%20year.png "passengers flow by weekday over year")

Passengers flow on weekends is about 35 % lower then on normal working day.

![alt text](docs/Passengers%20flow%20by%20weekday.png "passengers flow by weekday")

At summer time passengers flow decreases. On 9 month Thursday and Friday is almost 20 % passengers flow increase compared with begining of the week, I guess it is because 2016-09-01 (Thursday) is start of the session.

## Passengers flow by hour

I am interesting how passengers flow changes depending on time of the day over year and single month. At this point I am analyzing only count of passengers IN value. Hourly counts are grouped into to ranges of 4 hours.

![alt text](docs/Passengers%20flow%20by%20hours%20over%20year.png "passengers flow pver year")

![alt text](docs/Passengers%20flow%20by%20hours%201.png "passengers flow 1 month")

![alt text](docs/Passengers%20flow%20by%20hours%202.png "passengers flow 2 month")

![alt text](docs/Passengers%20flow%20by%20hours%203.png "passengers flow 3 month")

![alt text](docs/Passengers%20flow%20by%20hours%204.png "passengers flow 4 month")

![alt text](docs/Passengers%20flow%20by%20hours%205.png "passengers flow 5 month")

![alt text](docs/Passengers%20flow%20by%20hours%206.png "passengers flow 6 month")

![alt text](docs/Passengers%20flow%20by%20hours%207.png "passengers flow 7 month")

![alt text](docs/Passengers%20flow%20by%20hours%208.png "passengers flow 8 month")

![alt text](docs/Passengers%20flow%20by%20hours%209.png "passengers flow 9 month")

![alt text](docs/Passengers%20flow%20by%20hours%2010.png "passengers flow 10 month")

![alt text](docs/Passengers%20flow%20by%20hours%2011.png "passengers flow 11 month")

![alt text](docs/Passengers%20flow%20by%20hours%2012.png "passengers flow 12 month")

As expected single day data are distributed normally. Highest passengers flow is between 12 and 16 hours. Least passengers flow is in the early morning. By the way biggest passengers traffic flow between 0 and 4 hours is on weekends, especially on saturdays. Passengers flow depends on the day of the week.

## Passengers flow correlation between month

Let's inspect which months are similar to each other based on passengers flow on week days.

![alt text](docs/Passengers%20flow%20correlation%20between%20month.png "passengers flow correlation")

Correlation heatmap shows that 9 and 12, 8 and 11, 3 and 11, 2 and 10 months passengers flow was very similar. On the other hand 3 and 7, 6 and 7, 8 and 7, 11 and 7 months passengers flow was different. 6, 7, 8 months are very different, because passengers traffic flow on those moths was lowest.

## Passengers flow trend

I guess no trend occurs in the data. Passengers flow rise and fall with no particular pattern, but lets test that.

![alt text](docs/passengers%20flow%20trend.png "passengers flow trend")

After performing linear regression analysis I can see that no linear trend exists.