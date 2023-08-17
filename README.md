# An Analysis on the NBA and what Stats may reveal about certain players

## Overview

I've always been interested in basketball, and specifically, NBA players. NBA players are the best at their sport in the world, but how do they become the best. What stats tell us this?

Take for example, advanced stats that we have today. Whether they be Nate Silver's RAPTOR or Basketball Index's LEBRON stats, I wanted to analyze how good NBA players could be relative to others. To do this, I went through Basketball Reference's stat sheets and analyzed how likely it would be for each individual player in the NBA to receive the annual NBA MVP vote. Note that this was done entirely based on historical data, which was web scrapped from basketball reference's API and webtables, in guidance with their policy on API.

The analysis tells a picture on how NBA players, specifically the MVP, is picked and what stats specifically let us know the reason that voters might pick them, without any subjective bias like the "eye test" or "dominance" of a player.

<p style ="text-align: center;">Credit to [u/sh00ner](https://www.reddit.com/user/sh00ner/) for the Illustration</p>


=======
![rs=w-1209,h-1868](https://github.com/kev374k/Hardwood_Convergence/assets/54005848/c88b6d50-2461-4970-9268-c756f76ec789)
 
Credit to [u/sh00ner](https://www.reddit.com/user/sh00ner/)
### Part 1 - What the Analysis is About

At the core, basketball is about getting the ball through the hoop. 

Yet, it is realistically signficiantly more difficult than that. If making a shot was all that mattered, why wouldn't I just want a team that was exclusively centers, who typically have the highest chance of making any shot they take? In fact, compared to point guards, which have a median shooting percentage of 0.4105, Centers have a median shooting percentage of 0.533. Yet coaches play guards because of both their size and their speed, along with their playmaking, which most centers lack severely. The real beauty in basketball lies in the *tactics*, which shape how the game is played. 

Regardless of positions and other advanced stats, I wanted to measure what made the most *valuable* players in the league. Are they the ones with the ball in their hands all of the time? Or are they more off-ball players, who rely on their teammates to get them the ball to shoot?

What factors are most reliant on being the "MVP?". Do MVPs need to play a certain amount of minutes, or does success, in terms of their winning record matter more? In this analysis of NBA MVPs and trying to place the value of a player in a single number, I strived to answer all of these questions.

### Part 2 - Web Scraping

This part deals with getting the data necessary for the analysis. A lot of times, this is the most difficult portion of the process. 

As an avid NBA fan, I've always looked up information on players through [Basketball Reference](https://www.basketball-reference.com), and fortunately, through a thorough amount of searching, I found that Basketball Reference is very useful in this manner. They frequently allow people online to scrap their data, as long as they follow certain rules. 

The main rule was a solution against bots: Not scrapping more than 20 times in one minute.
