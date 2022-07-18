#WeeklyMileageDistribution 

Utilizes Strava API and multilinear regression to generate a mileage breakdown based on an input for athlete based on year's activity. As a
runner at Columbia University who is building mileage I found it annoying to add up the numbers each week based on what the coach send out. For those 
still confused, input is ex. 75 (miles for the week) output: 

![Screen Shot 2022-07-18 at 6 21 55 PM](https://user-images.githubusercontent.com/107092609/179627260-23c449c5-035e-4227-a946-e4afb1c19c91.png)

A breakdown of how much to run each day. 14 outputs, 7 days a week: morning / evening run. Obviously running 75 miles a week nobody is doing an evening
run of .35 miles so you'd have to chose a day or two to stack the evening runs all together. Breakdown works quite well for my case, sunday longest run & wednesday 2nd longest run and saturday is the lightest load day; and its consistent for the outputs. 

First you authorize the user, then fetch the past years worth of activities. You filter out so it's only runs and add to the database which created such that cuts off any half weeks at beginning / end (starts on monday / ends on sunday). Add data to dataframe and find if the person doubled (morning & evening run). Add create the 14 feature input into the machine learning algorithm. And at the end predict whatever value (mileage) you'd like to run for that week. 
