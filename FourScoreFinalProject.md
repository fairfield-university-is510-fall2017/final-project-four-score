# final-project-four-score
final-project-four-score created by GitHub Classroom

# NBA Championship Data

## Description/Purpose
  The purpose of this project was to create a database using NBA Championship Finals Data back to 1980. We chose to use this dataset as the topic was of interest to us and importantly, the file contained enough data where we could create an efficient database from, yet allowing flexibility where we can tie relevant data from a different source. Data loaded into our initial database was gathered from Kaggle which included every champion, and a number of stats for each game played in the championship per year. Based on this data, we decided to extract data from a second dataset by migrating a web csv without actually downloading the content. The additional data contains details on players that have played on all teams for each year. From there, we will pull players from the web csv into our championship data to pair player information for each winning team. 
  

 ## Steps Taken
 
 ### Finding the data
 
1. Our first step was to find the data that we wanted to insert into our database. Once retreiving the csv, we ensured that the data was normalized by and making sure it followed the BKNF format and conditions. 
 
  --> The Kaggle DataSet that we have used to create, insert and load our tables can be found [here.](https://www.kaggle.com/daverosenman/nba-finals-team-stats)
  
2. After finalizing the file, we wanted to find an online source where we'd be able to retrieve relevant and tie it to the data that we would import from kaggle. We were able to find individual player data info which would would create a player table from and pull stats from individual plays from a winning team within a respective year. 

--> Our Player Dataset used for the above was retrieved from Data.World which can be found [here.](https://data.world/jgrosz99/nba-player-data-1978-2016)

3. After finding our data, our next step was to create our data model and ERD which would outline our database design. Given that we were only able to design 4 legitmate tables into our database from our Champions Data from kaggle, we decided to create our 5th table using data from both tables. In doing so, we modified our orignal csv file to include a TeamCode column which we'd use as a primary key in our team table and also pair to the 'tm'(Team) column from the player data which identified teams as codes and not by their actual name. 

Below is a view the ERD created to design our database. 


