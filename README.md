# Hardwood_Convergence
An analysis on how well NBA players do on the court and how valuable they are to their teams. Using www.basketball-reference.com for all stats, including previous MVPs, the season stats(all players), and advanced stats for players

# File is Divided into 4 main notebooks. 
## The First is the Web_Scrapping.ipynb notebook, which is where we got all of the data, which was placed into files/full_player_stats and files/team_records from 1991-2023(2023 season not over yet). We used selenium and requests to web scrap the website and take the tables needed in order to get the correct HTML files and convert them into CSV

## The Second and Third notebooks are the Data_Cleaning.ipynb and Advanced_Stats_Scrapping.ipynb notebooks, which clean the data from the player stats and the MVPs as well as gets the advanced stats like VORP(Value Over Replacement Player), WS(Win Shares), and more in order to help the model more accurately predict the MVP

### This is divided into two files because we wanted to separate the advanced stats and the normal player stats, because we want to see the difference in a model without advanced stats and one with advanced stats would fare compared to the actual MVP

## Finally, the last notebook is the machine_learning.ipynb, which contains the model that we used. We used Ridge(), an extension of the linear regression model from sklearn.linear_model, which takes multiple coefficients from the columns and correlates how effective each is to predict the MVP


