 # Football Player Market Value Prediction

## Problem Statement
In the English Premier League, May - July represents a lull period due to the lack of club football. What makes up for it, is the intense transfer speculation that surrounds all major player transfers today. You must have seen "Moneyball", where Peter Brand explains Billy Beane that "Its about getting things down to one number using stats the way we read them (players), we find value in player nobody else can see." Therefore, an important part of negotiations is predicting the fair market price for a player and perhaps perform EDA for this.

## EDA (Important Ones)

1. ### Players in every club and position

    ![clubvsplayers](/figures/clubvsplayers.png)

   -  The bar graph above shows how many players are there in every   club and the variation of player's positions.
        - x axis --> club names
        - y-axis --> total number of players.

    The variation of player position are distinguish by different color in each bars. The colors code for players position is explained on the righ side of the chart.
    `Arsenal , Everton , and Huddersfield have the biggest number of players with 28 players . Burnley has the lowest number of players with 18 players.`

2. ### Distribution of Player's Ages

    ![playerhist](/figures/playerhist.png)

    A typical histogram of players age can be called "Edge Peak Histogram".
    - The edge peak distribution looks like the normal distribution except that it has a large peak at one tail.
    - As it is shown in the histogram, the distribution of age is increased untill it meet the peak point at the age between 25-30. 
    - There is one bar that significanly higher than the others, that is why the histogram above can be calles Edge peak histogram.


3. ### Top 10 Player Market Values (2017-2018)

    ![top10players](/figures/top10players.png)

    - The bar chart above shows the top 10 market value for each player.
        - x-axis --> players name
        - y-axis --> market value

    It appears that Eden Hazard and Paul Pogba have the biggest market value, which is 75. They are followed by Alexis Sanchez on the 3rd position.

4. ### Average Market Value of every club

    ![avgmarketvalue](/figures/avgmarketvalue.png)

    - The bar chart above shows sorted average of market value for 
      each club. 
        - x-axis --> club names
        - y-axis --> average market value
    
    It appears that ManCity and Chelsea, which are famous for spending money for a star player have the biggest average market value. They are followed by Totenham on the 3rd position. Burnley, Brighton, and Huddersfield are sitting in the lowest 3.

5. ### Most Viewed Players

    ![mostviewdplayers](/figures/mostviewdplayers.png)

    - The bar chart above shows the top 10 most view players.
        - x-axis --> Player names
        - y-axis --> Market value

    It appears that Wayne Rooney has the biggest market value, followed by Paul Pogba and Dele Alli on 2nd and 3rd position.

6. ### FPL 10 most valuable players

    ![mostvaluableplayers](/figures/mostvaluableplayers.png)]

    - The bar chart above shows the top 10 highest FPL value for each 
      player. T
      - x-axis --> players name
      - y-axis --> FPL value
      
    It appears that Harry Kane has the biggest FPL value, followed by Alexis Sanchez on the 2nd position. As it is shown in the graph above, there are 3 Belgium players that sit in this position, who are Eden Hazard, Kevin de Bruyne, and Romeru Lukaku while the FPL value top 10 position is dominated by foreign players. The only local player who is in this position is only Hary Kane.

7. ###  Average of FPL value for every club

    ![averageFPL](/figures/averageFPL.png)

    - The bar chart above shows sorted average of FPL value for each  
      club. 
      - x-axis --> club names
      - y-axis --> average FPL value

    It appears that ManCity and Chelsea have the biggest average market value. They are followed by Totenham on the 3rd position and the 3 promoted clubs are sitting in the lowest 3.

8. ### Correlation Matrix

    ![correlationmatrix](/figures/correlationmatrix.png)

    - Each square shows the correlation between the variables the variables on each axis. 

    - Values closer to zero means there is no linear trend between the two variables.

    - The close to 1 the correlation is the more positively correlated they are the closer to 1 the stronger the relationship is **larger the number and darker the color the higher the correlation between the two variables.**

9. ### Nationality of Players

    ![nationality](/figures/nationality.png)

    - The bar chart above shows the count of players w.r.t their nationality in the FPL.
        - x-axis --> countries
        - y-axis --> count for players
    
    We can conclude that England has highest i.e. maximum number of players.











