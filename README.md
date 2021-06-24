![HOF_cover](https://user-images.githubusercontent.com/67566192/109255123-5990fe00-77c1-11eb-94e9-254e184c0b78.jpg)

# Predicting Wins in MLB 

**Author**: Michael Tiernan

## Brief History
Betting on sports has a long history despite the fact that it has only recently become legal to do so outside of Nevada (which legalized it in 1942). New Jersey became just the second state in the US to legalize sports betting following a US Supreme Court ruling in May of 2018. This was a major court decision that opened the floodgates for more states to follow and billions of dollars to be generated doing so. As of today, June 24, 2021, 22 states have legalized sports betting in the US. The rest of the US has either passed or introduced a bill to legalize the industry with the exception of only three states (Idaho, Utah, Wisconsin) who have not. 

For those not familiar with the industry, a sportsbook (ex. DraftKings, William Hill, FanDuel, Barstool) creates betting odds based on their own machine learning models for the user to then wager money on. If the two teams are very similar and there is no clear favorite, the odds for that game would be close to even. When the odds are even, a $100 bet will return a $100 payout (if the team you bet on wins). But what if one team is heavily favored? When the best team has a game against the worst team, the odds for that game have to account for this disparity and the way they do that is adjusting the odds to lets say -200, which means that your $100 bet now only returns a $50 payout. By doing so, one may be persuaded to then bet on the underdog in this scenario because the odds on the underdog will be +150, which means your $100 would return $150 payout. By adjusting the odds, the sportsbook is looking to have an even amount of action on each team because this almost assures them a profit due to the fact that it is expected that the favorite will win, in which case they only have to payout $50 in the 2nd scenario, but at the same time collecting the $100 lost bet from the underdog bettor. This, coupled with the resources and mastery that the sportsbooks have in creating the odds, is what makes betting on sports so difficult in terms of being profitable over the long-term for the average user.

## Business Problem
Given this brief history, it is clear that the average bettor has an uphill battle to long-term profitability. For my analysis, I am looking to answer the two questions below:

    1) What are the best predictors for season total wins?
    2) What are the best predictors for individual game wins?

Like any other game, whether it be casino, board games, or competitive sport, the intelligent player is going to  look for a competitive advantage. Within the sports betting industry, the inexperienced bettor likely makes their wagers based off of gut intuition. The intermediate bettor may incorporate research from articles read or a comparison of some surface-level stats, but the true competitive advantage comes from a deep-dive into the data, using machine learning algorithms to account for as many factors/predictors as possible. 

This is the strategy I will continuously build upon in pursuit of creating a highly competitive algorithm for long-term sports betting profitability.
 

## Data
Yearly team total stats as well as a history of every game log dating back to the start of the 2014 season was used in my analysis.
The data used in this analysis comes from [Lahman's Baseball Database](http://www.seanlahman.com/baseball-archive/statistics/) as well as [baseballsavant](https://baseballsavant.mlb.com/leaderboard/custom?year=2019,2018,2017,2016,2015&type=batter&filter=&sort=4&sortDir=desc&min=q&selections=xba,xslg,xwoba,xobp,xiso,exit_velocity_avg,launch_angle_avg,barrel_batted_rate,&chart=false&x=xba&y=xba&r=no&chartType=beeswarm). After joining, manipulating, and feature engineering, I ended up with _____ rows and ___ features (or stats) used to predict season total wins. 


## Method
For this project I stuck to the CRISP-DM method. After retrieving the data, I cleaned and joined a number of different databases (Lahman's is an extensive database made up of 20+ csv files) in order to create my final database to use for modeling. 

For modeling, I chose to work mostly with DecisionTree classifiers. Logisitc regression was used intially, but due to the high multicolinearity effecting many of my main features, I had to focus mainly on DecisionTrees. I prioritized accuracy as my main metric, but also set out to have high recall score as well so that my model was focused on rewarding those who deserve to be in the HOF and making sure we were not missing them in my binary classification models; HOF or not.

**The following players were removed from the data after running a couple models with them included. The players were those who have HOF numbers, but are currently banned by the MLB HOF committee due to Performance Enhancing Drugs (PEDs) use or other reasons:
(Pete Rose, Alex Rodriguez, Barry Bonds, Sammy Sosa, Mark McGwire, Manny Ramirez, Rafael Palmero, and David Ortiz).

## Findings
I found the stats both by position and overall playing career.
![stats_subplots](https://user-images.githubusercontent.com/67566192/109269259-40487b80-77da-11eb-9537-db72fbce3be8.png)

Looking at the visuals above, it is clear that HOF players are vastly better than the rest of the field in every stat, however, there are different requirements depending on position i.e. Catchers ('C') not heavily rated on the number of hits or Shortstops ('SS') not heavily rated on homeruns. 



![hits](https://user-images.githubusercontent.com/67566192/109270845-a6ce9900-77dc-11eb-9621-0721baae4381.png)

As you can see from this second graph above, the vast majority of MLB leaders in career hits are HOFers (HOFers denoted by orange plots). 
**Also note one of the players noted above that is banned from the HOF, Pete Rose is the all-time leader in hits, but not a HOF (blue plot).


## Recommendations
![feature_importances_best](https://user-images.githubusercontent.com/67566192/109297156-8cf27d80-77ff-11eb-9032-08d929033f29.png)

The most important stats when it comes to evaluating a HOF player is Hits, Runs, and All-Star games made. With this newfound, I recommend to my client that they should use these metrics when negotiating their current contracts as well as look for active and upcoming players with these stats in mind. They will pay off large when these players sign their hundred-million dollar contracts! 

## Conclusion and Future Work
While my best model performed effectively with a 86% recall and 94% accuracy, it does not meet the requirement of within 5% to reject the null hypothesis. 

I am happy with the performance of my model, but with more time I would have loved to go deeper into the world of sabermetrics and work with stats like OPS+, WOBA, and WAR. These are stats that have come to more accurately define a player's ability, but I was unable to find this data, and calculating them is an extensive task because you must account for the time periods in which these players played in order to accurately implement these stats.
    
