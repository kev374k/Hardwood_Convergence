# An Analysis on the NBA and what Stats may reveal about certain players

## Overview

I've always been interested in basketball, and specifically, NBA players. NBA players are the best at their sport in the world, but how do they become the best. What stats tell us this?

Take for example, advanced stats that we have today. Whether they be Nate Silver's RAPTOR or Basketball Index's LEBRON stats, I wanted to analyze how good NBA players could be relative to others. To do this, I went through Basketball Reference's stat sheets and analyzed how likely it would be for each individual player in the NBA to receive the annual NBA MVP vote. Note that this was done entirely based on historical data, which was web scrapped from basketball reference's API and webtables, in guidance with their policy on API.

The analysis tells a picture on how NBA players, specifically the MVP, is picked and what stats specifically let us know the reason that voters might pick them, without any subjective bias like the "eye test" or "dominance" of a player.

![rs=w-1209,h-1868](https://github.com/kev374k/Hardwood_Convergence/assets/54005848/c88b6d50-2461-4970-9268-c756f76ec789)
 
Credit to [u/sh00ner](https://www.reddit.com/user/sh00ner/)
### Part 1 - What the Analysis is About
 

### Part 2 - Web Scraping

This part deals with getting the data necessary for the analysis. A lot of times, this is the most difficult portion of the process. 

As an avid NBA fan, I've always looked up information on players through [Basketball Reference](https://www.basketball-reference.com), and fortunately, through a thorough amount of searching, I found that Basketball Reference is very useful in this manner. They frequently allow people online to scrap their data, as long as they follow certain rules. 

The main rule was a solution against bots: Not scrapping more than 20 times in one minute.
