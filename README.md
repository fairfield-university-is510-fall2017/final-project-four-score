# final-project-four-score
final-project-four-score created by GitHub Classroom

## Description/Purpose

The purpose of this project was to create a database using NBA Championship Finals Data back to 1980. We chose to use this dataset as the topic was of interest to us and importantly, the file contained enough data where we could create an efficient database from, yet allowing flexibility where we can tie relevant data from a different source. Data loaded into our initial database was gathered from Kaggle which included every champion, and a number of stats for each game played in the championship per year. Based on this data, we decided to extract data from a second dataset by migrating a hosted csv without downloading the content. The additional data contains details on players that have played on all teams for each year. From there, we will pull players from the hosted csv into our championship data to pair player information for each winning team. 
 
## Steps Taken

  ### Finding the data
 
 1. Our first step was to find the data that we wanted to insert into our database. Once retreiving the csv, we ensured that the data was normalized by and making sure it followed the BKNF format and conditions. 
 
 * The Kaggle DataSet that we have used to create, insert and load our tables can be found [here.](https://www.kaggle.com/daverosenman/nba-finals-team-stats)
  
 2. After finalizing the file, we wanted to find an online source where we'd be able to retrieve relevant and tie it to the data that we would import from kaggle. We were able to find individual player data info which would would create a player table from and pull stats from individual plays from a winning team within a respective year. 
 
 * Our Player Dataset used for the above was retrieved from Data.World which can be found [here.](https://data.world/jgrosz99/nba-player-data-1978-2016)
 
  ### Designing the Database

 3. After finding our data, our next step was to create our data model and ERD which would outline our database design. Given that we were only able to design 4 legitmate tables into our database from our Champions Data from kaggle, we decided to create our 5th table using data from both tables. In doing so, we modified our orignal csv file to include a TeamCode column which we'd use as a primary key in our team table and also pair to the 'tm'(Team) column from the player data which identified teams as codes and not by their actual name. 
 
 Below is a view the ERD created to design our database....
 
 ![ERD](https://github.com/fairfield-university-is510-fall2017/final-project-four-score/blob/master/NBA_ERD%20.png) 
 
 4. Using the ERD Database Model we created, we were able to write the [DDL](https://github.com/fairfield-university-is510-fall2017/final-project-four-score/blob/master/DDL.ipynb) to create the database connection, construct the tables, and identify keys and column types for each table. Before populating into our relational tables, we created a data table, NBAData, which would include all data imported from the csv file. 
 
  ### Importing the Data into Tables 
 
 5. After creating the tables and creating pragmas to endsure keys are correctly identifed, we imported the data into our tables using inserty functions in our [DML](https://github.com/fairfield-university-is510-fall2017/final-project-four-score/blob/master/DML.ipynb)  notebook. Our first step was to grab the data from the ChampionsData csv file and run .mode and .csv commands in SQLite3 follwed by a .dump commmand which would return all data from the csv and import into our data table (NBAData). We extracted the  insert statements from terminal and pasted into our DML file. Once inserted, we imported into our 4 main tables to import the data from the NBAData table. In order to import into the 5th table, we needed to pull data from both our csv and the web hosted csv from Data World. This wwas done by using the .to_sql command to import the data from the hosted csv into a new table and converting it to a data frame. From there, we were able to import into the Players table using data from both sources.
 
 6. To ensure that the tables included accurate data, we ran a number of "select *" queries from each table.
 
  ### Analysis 
 
 7. Since we used an interesting dataset, we decided to test out accruacy even further by discovering cool [facts](https://github.com/fairfield-university-is510-fall2017/final-project-four-score/blob/master/Analysis.ipynb) on NBA championship teams and players from popluar teams and from out current favorite teams. We found this to be interesting because we could find out any fact about winning teams back to 1980 and all players who have played on the winning team. 
 
 
 ## Things We Learned/Challenges
 - It is very important to have your database well designed base on the rule of normalization. The order of creating tables and identifying weak and strong entities as well as levels among the tables
 - It is important to know more than one method of solving the same problem because sometimes not all methods work with what you are trying to do
 - Gather facts,data and decide on a purpose before diving into to code.
 - Consistency with colmun titles(especially when join columns can get confusing) 
 - Always ask for help!!! Whether it is from the professor, teammates or google. Asking early prevents you from misuse of time and identifying the problem early on  
 
 
 
 
 *IS 510 Final Project Completed by Nastaja Johnson and Engu Chen*
