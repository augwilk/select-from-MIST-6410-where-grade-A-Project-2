# Team 8 Mist 4610 Group Project 2

## Team Name: 
select * from MIST4610 where grade = A; 

## Team Members:

1. Gus Wilkerson [@augwilk](https://www.github.com/augwilk)
2. Emma Calleja [@EmmaCalleja](https://github.com/EmmaCalleja)
4. Hannah Conley [@Hmc98563](https://github.com/Hmc98563)
5. Rahil Patel [@rahilp0215](https://github.com/rahilp0215)
6. Marc Ordonio [@marcord245](https://github.com/marcord245) 


## Problem Description:

The task at hand:
Today, college football data is spread across multiple platforms and sources, making it difficult to get a clear and accurate picture of the sport. Since this approach is broken up across platforms, it is difficult to access and analyze key statistics or trends over time. To address this issue, the NCAA has launched a project to create an essential database of Division 1 college football statistics.
Specifically, the project aims to create a unified data repository for all D1 conferences, players, and head coaches, including in-depth statistics such as NIL, wins, losses, and game statistics among others.


## Data Model

Explanation of data model: 

Our data model is based around the landscape of college football as we see it. College football is made up of a handful of conferences each of which has several programs as shown by the one to many relationship established between the conference and program entities. Each season a program has a different team. The team entity contains pertinent information for a specific team for a given season including what university of the team and the tally of their wins and losses. Every season, a conference has 1 team crowned as the conference champion.

Every program has another program taht is its arch rival indicated by the recursive 1 to 1 relationship within the program entity. Programs also need several coaches to operate (i.e. position coaches, coordinators, trainers) but each has just one head coach as shown by the one to one relationship between the coach and program entities. Coaches have a name, a salary, and a title of their position.

Each team plays in multiple games in a year and each game has two teams. The weak entity linking the many to many relationship between team and game is the team_game entity which stores each team’s individual score in the specific game. The team_game entity also has a 1 to 1 relationship to team which shows the opponent of the team in that game.

Because of the transfer portal, players can now be on multiple teams over the time of their collegiate career but only one team per season. The playerYear entity links many players to many teams and vice versa, storing the date they joined and left the team if applicable. The playerYear entity stores information that is pertainent to a player fro a given year but may change next year such as the team tehy are on, their number, or even their height and weight.

The player table stores personal information for each player that likely won't change year over year such as their name, birthdate, contact information, and position. A player can be a mentor of another player (or several other players). This is shown by the 1 to many recursive relationship within the player entity.

A player plays in many games and a game has many players involved. The weak entity between these two entities is gameStats which stores the offensive yardage statistics each player records in each game they play. Passing yards, receiving yards, and rushing yards for each player are stored here.

A player can also now have many NIL deals with several companies. One company (stored in the Sponsor table) also has the ability to sponsor many players. A sponsor has a company name and a unique id. To link the many to many relationship between Sponsor and player there is the NIL table. The NIL table stores the id of the deal as well as the agreed upon dollar amount for the contract between a company and a player.

Our data model stores a range of data regarding college football over several seasons which could be useful for a school administration, third party company interested in sponsoring athletes, or the everyday college football fan!


![Project 2 Diagram final](https://github.com/user-attachments/assets/dd5b17b6-ad1c-4e2d-9c5f-850c42edb2bd)


## Data Dictionary:
![Screenshot (103)](https://github.com/user-attachments/assets/d488680b-b98c-4ab9-80ef-b6e8ca6fea76)


![Screenshot (104)](https://github.com/user-attachments/assets/c9c65e87-58d3-4e88-99f1-471eb9c3858d)


![Screenshot (106)](https://github.com/user-attachments/assets/fa905a5c-ec0a-4979-bb74-92e29149c2f5)


![Screenshot (107)](https://github.com/user-attachments/assets/9f9afbae-150d-4f78-9ce8-c9472e533976)


![Screenshot (108)](https://github.com/user-attachments/assets/129d9386-288d-4039-bb36-10a121da0af6)


![Screenshot (111)](https://github.com/user-attachments/assets/e6ebfb92-4a5c-429a-960d-63a1683508e6)


![Screenshot (113)](https://github.com/user-attachments/assets/c927be2f-b171-4760-9328-37352f939c3c)


![Screenshot 2024-12-01 162828](https://github.com/user-attachments/assets/3d7c46c6-9fd0-4384-8afb-d1059401d28a)


![Screenshot 2024-12-01 164142](https://github.com/user-attachments/assets/cabf376c-ccc1-4361-9f36-95d5a9598c90)


![Screenshot 2024-12-01 165152](https://github.com/user-attachments/assets/a9d55a3a-5a11-4789-a51f-ed64f2f3b414)


![Screenshot 2024-12-01 172002](https://github.com/user-attachments/assets/043bea59-46cd-4ccf-97c7-148ff0e403a2)


![Screenshot 2024-12-01 170604](https://github.com/user-attachments/assets/9a817678-e92f-48b8-b570-c216411d9e80)


![Screenshot 2024-12-01 170835](https://github.com/user-attachments/assets/d96867dc-c40b-442b-8149-debe6eb02594)


## Queries:
1) Query 1 shows conference champion trends, with teams added
   
![image](https://github.com/user-attachments/assets/4305d710-5f7c-4a70-a23b-c97facabd48a)

This query would be useful for 

2) Query 2 shows players with the most stats and their NIL sponsor amount

![Players with most stats and their NIL sponsor amount](https://github.com/user-attachments/assets/5ee2f443-3035-43b5-a0a2-d968ce924d68)

This query shows

3) Query 3 shows the data from schools that include their win/loss record as well as the points scored in games. 

<img width="491" alt="Screenshot 2024-12-01 at 6 22 51 PM" src="https://github.com/user-attachments/assets/c6170fc7-d32c-4ca7-b742-cceb2ecc0bde">

This query is important for creating data-driven insights and knowing where to allocate resources and funding.

4) Query 4 takes displays the list of all players including those who do and do not have NIL deals and displays their average receiving yards and average minutes played per game if they are a runningback or widereciever. It also provides their ID, full name, and the amount of their NIL contract if they have one. 

![Screenshot 2024-12-03 102701](https://github.com/user-attachments/assets/d2b91d39-46e6-4a54-85a2-e0f05440157f)

This query would be useful for companies interested in signing a new NIL deal with a player who has good receiving stats and gets lots of playing time. They can review who has the best perfromance in these statistical categories that doesn't yet have a NIL deal. They can also review the NIL amount of similar players. Using this data, a company might decide that they want to sign Malik Neighbors to an NIL deal since he averages the most recieving yards per game out of any player without a contract. They could also use this data to decide they shoudl make an offer for about $40k since that was a similar player has agreed to.


## Visualzations:

1. Visualization 1 displays a bar chart of the win totals of all the teams in the SEC, ACC, and BIG 10 conference and highlights those that would be eligible to make the college football playoff in season 1 using the 12 team playoff format. The win cutoff for playoff teams this year would be 10 wins. The teams with sufficient win totals are highlighted in blue while the other teams which would not qualify within our database are in a less noticable grey.

![Screenshot 2024-12-02 200854](https://github.com/user-attachments/assets/4afe587a-4cb2-410e-aa3b-d1a1f3199998)

This Visualization could help college football playoff committee members to distinguish which teams are deserving to make the playoff for this year. It also highlights the most competitive conferences. Under this model, we can see that 3 BIG 10 teams would make the playoff to the SEC's 2 and the ACC's 1. This information could also help a highschool player who wants to look at what conference would give them the ebst chance of making the playoff. They may use this model to decide that they want to go play for a BIG 10 school rather than an ACC school because of the competitive advantage.

2. Visualization 2 shows average quarterback performance based on the birth year of the quarterback. It maps both average passing yards per game in blue (with the axis on the left) and average rushing yards per game in orange (with the axis on the right).  

![Screenshot 2024-12-02 201028](https://github.com/user-attachments/assets/aee8db2f-ea2a-4fee-b506-530d719d6e94)

This Visualization allows coaches and recruiters to analyze what age is ideal for a college quarterback. We can perfrom analysis on this graph to determine that there is a significant dip in performance of players who are born in 2000, being the second to youngest age group who are likely sophmores. While at first this may seem odd, it does make sense when you think about the quarterback position. This dip in performace could be because second year quarterbacks have a year of film under their belt that opposing teams could use to game plan against them. Regardless of teh reason, thsi graph raises interesting questions that coaches and recruiters may want to consider when thinking about the age of the quarterback they plan to start.

3. Visualization 3 maps the salary of a schools head coach per win under their belt. Salary per win is a calculated field made from dividing the total annual salary of a head coach divided by the number of wins his team records for the season. Schools with coaches in the top 25% of this statsitic are highlighted in white for review of unfair overpayment.

![Screenshot 2024-12-03 094733](https://github.com/user-attachments/assets/fe6770b8-1400-436e-b658-84b4e5270133)

This visualization is useful for program admisistrators and atheltic directors to use to determine if they are over paying thier head coach. By dividing the coach's salary by the number of their wins, the administration can basically see how much it costs them per win. If a program's coach is in that top 25 percentile for this statistic, they will probably want to review their coach's contract and reassess if they are getting teh return on investment that they want. For coaches with winning records, maybe it is worth overpaying them a bit. But for coaches with losing records, a demotion may be in order.

4. Comprehensive Data Visualization Dashboard

![Screenshot 2024-12-02 201044](https://github.com/user-attachments/assets/5436ddcb-2f1c-4c5a-aec6-99b7aac40b06)

This dashboard is useful for authority figureswho want to comprehensively review relevant data for their team or school. The dashboard is a place where lots of data can be looked at and ocmpared at a high level. For example, an atheletic director fro a school like Nebraska may be looking to review the contract of their schools head coach. The AD could see that their coach has the highest salalry per win which may indicate that they are overpaid. The AD coudl then review the total wins bar chart and see that Nebraska actually has one of teh lowest win totals out of any school which likely means their head coach is seriously over paid. However, the AD may want to check the age of their starting quarterback before talking with the coach in case the reason for the losses is because the QB is in his second year when QBs tend to struggle.
This is just one potential example where the dashboard could be useful.


## Database information:

Name of the database: cs_aww39979

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL SP1();
