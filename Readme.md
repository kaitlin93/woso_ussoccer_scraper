# US Soccer Game Scraper

A script to scrape the USWNT results page of US Soccer's website to get information about past games and save it in a database.


## Installation

To install, use pip3 to install the dependencies listed in requirements.txt. 


## Model Descriptions
There are three models generated by the scraper: a Game object, which contains information about each individual game, a Player object, which describes a player's performance in each individual game, and a Goal object, which contains information about each individual goal scored.

### Game
* id (int) -- unique identifier for the game
* attendence (int)
* date (datetime)
* competition (str) -- the tournament the game was played in, if applicable, or "International Friendly"
* link (str)
* opponent (str)
* usa\_one (int) -- usa score at the end of the first half
* usa\_two (int) -- usa score at the end of the second half
* usa\_fin (int) -- usa score at the end of the game
* opp\_one (int) 
* opp\_two (int)
* opp\_fin (int)
* goals ("Goal") - all of the Goal objects for goals scored in the game
* players ("Player") -- all of the players listed as available for the game
* venue (str)
* weather(str)

### Goal
* id (int) -- a unique identifier for the goal
* scored\_by (str) -- the name of the player credited with the goal
* minute (int) -- the minute the goal was scored
* assist (str) -- the name of the player credited with the assist
* stoppage (int) -- if the goal was scored in stoppage time, this is how far into stoppage time it was
* team (str)
* game (Game) -- the related game object

### Player
* id  (int) -- a unique identifier for this appearance of this player
* name  (str)
* start (int) -- when the player entered the game. This value is -1 if they did not appear
* end  (int) -- when the player checked out of the game. This value is -1 if they played the entire match.
* game (Game) -- the Game object related to this appearance of the player
