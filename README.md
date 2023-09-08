# An Analysis on the NBA and what Stats may reveal about certain players

## Overview

I've always been interested in basketball, and specifically, NBA players. NBA players are the best at their sport in the world, but how do they become the best. What stats tell us this?

Take for example, advanced stats that we have today. Whether they be Nate Silver's RAPTOR or Basketball Index's LEBRON stats, I wanted to analyze how good NBA players could be relative to others. To do this, I went through Basketball Reference's stat sheets and analyzed how likely it would be for each individual player in the NBA to receive the annual NBA MVP vote. Note that this was done entirely based on historical data, which was web scrapped from basketball reference's API and webtables, in guidance with their policy on API.

The analysis tells a picture on how NBA players, specifically the MVP, is picked and what stats specifically let us know the reason that voters might pick them, without any subjective bias like the "eye test" or "dominance" of a player.


![rs=w-1209,h-1868](https://github.com/kev374k/Hardwood_Convergence/assets/54005848/c88b6d50-2461-4970-9268-c756f76ec789)

Credit to [u/sh00ner](https://www.reddit.com/user/sh00ner/)

=====

### Part 1 - General Info

At the core, basketball is about getting the ball through the hoop. 

Yet, it is realistically signficiantly more difficult than that. If making a shot was all that mattered, why wouldn't I just want a team that was exclusively centers, who typically have the highest chance of making any shot they take? In fact, compared to point guards, which have a median shooting percentage of 0.4105, Centers have a median shooting percentage of 0.533. Yet coaches play guards because of both their size and their speed, along with their playmaking, which most centers lack severely. The real beauty in basketball lies in the *tactics*, which shape how the game is played. 

Regardless of positions and other advanced stats, I wanted to measure what made the most *valuable* players in the league. Are they the ones with the ball in their hands all of the time? Or are they more off-ball players, who rely on their teammates to get them the ball to shoot?

What factors are most reliant on being the "MVP?". Do MVPs need to play a certain amount of minutes, or does success, in terms of their winning record matter more? In this analysis of NBA MVPs and trying to place the value of a player in a single number, I strived to answer all of these questions.

=====

### Part 2 - Web Scraping

This part deals with getting the data necessary for the analysis. A lot of times, this is the most difficult portion of the process. 

As an avid NBA fan, I've always looked up information on players through [Basketball Reference](https://www.basketball-reference.com), and fortunately, through a thorough amount of searching, I found that Basketball Reference is very useful in this manner. They frequently allow people online to scrap their data, as long as they follow certain rules. 

The main rule was a solution against bots: Not scrapping more than 20 times in one minute. 

So, in the Notebooks, I tried to make sure that I didn't overload the website and had to separate the steps in which I programmed the results. To begin, I wanted to look at the results of previous MVPs in which there were advanced stats for NBA players. In turn, I also used the *requests* module, in which I looped through the webpage to get the full HTML data, writting it into a new folder. After that, to get it into a much easier format to read and take the tables, I used BeautifulSoup in order to format it correctly.

Then, in order to go through to start a machine-learning model for predicting an MVP, we also need to process additional stats, like PPG, RPG, BPG, APG, etc. This means we would have to web scrape using Selenium on Safari, which doesn't use Chromium. This, along with other uses of the Web Scraper, allows us to format all of the HTML files into different folders in files, which include *"advanced_stats"*, *"full_players_stats"*, *"mvps"*, and *"team_records"*.

Here, we then compress all of the csvs from the different years into a folder called *"scrapped_csvs"*, because it's much easier to read it in pandas with the *read_csv* function.

=====

### Part 3 - Data Cleaning

Most of the time, the longest and hardest part of a data science project involves cleaning the data, which can often have many problems. In terms of this, since Basketball Reference is an affliated partner of the NBA, it is more reliable in that matter. 

First, let's look at the 5 .csv files we have. we have *"files/scrapped_csv/advanced_stats.csv"*, which tracks the Advanced Stats. *"files/scrapped_csv/mvps.csv"* tracks MVP data, including MVP shares, votes, and overall percentage of vote gotten. *"files/scrapped_csv/player_stats"* tracks stats that are traditionally depicted, like PTS, BLKS, REBS, ASTS, etc. *"files/scrapped_csv/team_record.csv"* tracks teh record of teams, because team success is also essential to how likely players are to get MVP votes. Finally, *"files/scrapped_csv/nba_abbreviations.csv"* has the abbreviations of NBA teams to make the merging of different DataFrames easier in the future.

In terms of the all of the data, we try to delete a lot of the columns that we deem unnecessary, including ones that are added when transferring everything into csv files. After that, we want to get rid of players who played for multiple teams in one year. Fortunately, we can create a function that gets rid of extra players who played for certain teams (for example, James Harden played for the Brooklyn Nets and Philadelphia 76ers in the 2021-2022 season. Basketball Reference makes this easy by averaging out the total stats from all the games the player played, which is typically placed into a row with a Team of "TOT") and only using the value that was the total average the player used.

Similarly, with the other csv files, we have to navigate certain problems like formatting, unclear names, as well as different team names (such as when the Charlotte Bobcats changed into the Charlotte Hornets in the 2014 - 2015 season). 

After all the cleaning of the main csv files, we can combine them into one main DataFrame, which we now can filter and sort out for main data. 

Finally, we put all of the information into one main csv file, which will be placed into the *"final_player_stats.csv"*, which has all of the main information that can be manipulated in the future.

=====

### Part 4 - Data Manipulation






