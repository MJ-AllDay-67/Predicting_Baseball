![presentation_cover](https://user-images.githubusercontent.com/67566192/124053146-b7db2100-d9ed-11eb-89b8-b80bde9ad8a9.PNG)


## Brief History
Sports betting has a long history despite the fact that it has only recently become legal to do so outside of Nevada (which legalized it in 1942). New Jersey became just the second state in the US to legalize sports betting following a US Supreme Court ruling in May of 2018. This was a major court decision that opened the floodgates for more states to follow and billions of dollars to be generated doing so. As of June'21, twenty-two states have legalized sports betting in the US. The rest of the US has either passed or introduced a bill to legalize the industry with the exception of only three states (Idaho, Utah, Wisconsin) who have not. 

For those not familiar with the industry, a sportsbook (ex. DraftKings, William Hill, FanDuel, Barstool) creates betting odds based on their own machine learning models for the user to then wager money on. If the two teams are very similar and there is no clear favorite, the odds for that game would be close to even (referenced as -100). When the odds are even, a $100 bet will return a $100 payout (if the team you bet on wins). But what if one team is heavily favored? When the best team has a game against the worst team, the odds for that game have to account for this disparity and the way they do that is adjusting the odds to lets say -200, which means that your $100 bet now only returns a $50 payout. By doing so, one may be persuaded to then bet on the underdog in this scenario because the odds on the underdog will be +150, which means your $100 would return $150 payout. By adjusting the odds, the sportsbook is looking to have an even amount of action on each team because this almost assures them a profit due to the fact that it is expected that the favorite will win, in which case they only have to payout $50 in the 2nd scenario, but at the same time collecting the $100 lost bet from the underdog bettor. This, coupled with the resources and mastery that the sportsbooks have in creating the odds, is what makes betting on sports so difficult in terms of being profitable over the long-term for the average user.

## Business Problem
Given this brief history, it is clear that the average bettor has an uphill battle when it comes to long-term profitability. I want to help close that gap. For my analysis, I'll start by answering the two questions below:

    1) What are the best predictors for season total wins?
    2) What are the best predictors for individual game wins?

Like any other game, whether it be casino, board games, or competitive sport, the intelligent player is going to  look for a competitive advantage. Within the sports betting industry, the inexperienced bettor likely makes their wagers based off of gut intuition and on a whim. The intermediate bettor likely has a plan and incorporates research to help confirm their original intuition and biases. The true competitive advantage comes from a deep-dive into the data, using machine learning algorithms to account for as many factors/predictors as possible and building on continuous findings to best predict the outcome of the next day's games. As a former athlete, I am of the mindset that there are always going to be intangibles that the data can not predict, but as you will see, the sportsbooks are extremely accurate.  

The good news is, there is room for opportunity, which my analysis will show. This is the strategy I will continuously build upon in pursuit of creating a highly competitive algorithm for long-term sports betting profitability.
 

## Data
Yearly team total stats as well as a history of every game log dating back to the start of the 2014 season was used in my analysis.
The data used in this analysis comes from [Lahman's Baseball Database](http://www.seanlahman.com/baseball-archive/statistics/) as well as [baseballsavant](https://baseballsavant.mlb.com/leaderboard/custom?year=2019,2018,2017,2016,2015&type=batter&filter=&sort=4&sortDir=desc&min=q&selections=xba,xslg,xwoba,xobp,xiso,exit_velocity_avg,launch_angle_avg,barrel_batted_rate,&chart=false&x=xba&y=xba&r=no&chartType=beeswarm). 


## Method
For this project I stuck to the CRISP-DM method. After retrieving the data, I cleaned and joined a number of different databases (Lahman's is an extensive database made up of 20+ csv files) in order to create my final database to use for modeling. 

For modeling, I tested many different models, but Random Forest with gridsearch resulted in the best findings for both my regression and classification analysis. For classification, I prioritized recall as my main metric, but also set out to have high accuracy score as well so that my model was focused on correctly predicting wins over losses.


## Findings
I was able to pull in vegas lines for season total wins going back to 2014. I did a deep analysis and compare to see how accurate the vegas lines actually are compared to the end result. 
![vegas_accuracy](https://user-images.githubusercontent.com/67566192/123279297-b8e3ee00-d4d5-11eb-9d54-f51167796a25.png)

As you can see, vegas is EXTREMELY accurate! In fact, when I compiled the data by team, cumulative of the years 2014 - 2019, the vegas lines for season total wins for each team were staggeringly accurate. Over this 6 year period, only 5 teams had a more than 5% difference when comparing the vegas line to the actual season total wins from that same year. 


## Recommendations
Bet one of the following teams when wagering on a team’s season total wins 	
- Detroit Tigers – 10% - Under
- Houston Astros – 9% - Over
- Cincinnati Reds – 8% - Under
- Milwaukee Brewers – 7% - Over
- San Diego Padres – 6% - Under

Bet on teams that have high run differential and produce a lot of RBIs

## Conclusion and Future Work
While I am happy with the performance of my models, I am a little underwhelmed by my findings. Baseball, like all sports, have a high level of parity, meaning that the majority of teams are average and bad teams often beat good teams and vice versa. Couple that with the variability in how a team can win and lose a game, and you can begin to understand how difficult predicting the sport can be. 
With that said, I am looking forward to continuously building on this project. In future, I will look to build my models up from the most micro level (1 pitch, 1 swing), taking into account pitchers, lineups, etc. in order to then build back up to the macro level (team stats) that I showed in my analysis here. 
    
