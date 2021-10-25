##  MSDS694 Dataset PUBG Match Deaths and Statistics

Create on: Oct 25                          Revision on: N/A

Group Number: 20

Student Name: Yufeng Xing

#### 1 Description

The current PUBG dataset is a public dataset that has the death records of over 720,000 competitive matches from the popular game PlayerUnknown's Battlegrounds (i.e. PUBG). 

PUBG is a first/third-person shooter battle royale style game that matches over 90 players on a large island where teams and players fight to the death until one remains. Players are airdropped from an airplane onto the island where they are to scavenge towns and buildings for weapons, ammo, armor and first-aid. Players will then decide to either fight or hide with the ultimate goal of being the last one standing. A bluezone (see below) will appear a few minutes into the game to corral players closer and closer together by dealing damage to anyone that stands within the bluezone and sparing whoever is within the safe zone.

This dataset provides two zips: `aggregate` and `deaths`.

- In deaths, the files record every death that occurred within the 720k matches. And each of the match has up to 100 players. That is, each row documents an event where a player has died in the match, and we can have 70m records of deaths in total.
- In aggregate, each match's meta information and player statistics are summarized (as provided by pubg). It includes various aggregate statistics such as player kills, damage, distance walked, etc as well as metadata on the match itself such as queue size, fpp/tpp, date, etc. This is a more detailed set we can use maybe for some meta information.

The uncompressed data is divided into 5 chunks of approximately 2GB each. For details on columns, please see the file descriptions. Based on the requirement of this group project, we can start from any single chunk larger than 2GB with more than 1m records.

#### 2 Resource

* [Kaggle gate page](https://www.kaggle.com/skihikingkevin/pubg-match-deaths): Basically the data we may use because it has already been generated
* [PUBG stats]([pubg.op.gg](http://pubg.op.gg/)): No one-step public dataset for downloading so we may need to crawl from this site by randomly choosing the players

#### 3 Reasons

* **Easy for EDA**: the game data is easier for EDA compared with the other data types. 
* **Few Features**: We don't have too many features so it can be easy to find a way out.
* **Accurate Data**: The gaming data is relatively more accurate compared with the other database like the 
* **Clear Intention**: The final goal in this game is quite clear: to survive and win. So all the data we have here do include a clear intention.
* **Simple Data Types**: For this set, what we have is just the pure data types rather than the complicated types such as audios, images, videos, and so on.

#### 4 Concerns

As it is said in the document of this dataset, the author starts with an initial seed player, and then use the seed player to scrape for all players that it has encountered in its historical matches. The author took a random subset of 5,000 players from this and then scrape for their historical games for the final dataset. So there may be potential bias in the data.

#### 5 Goals

Here is just a draft list of implementations we can think about,

- [ ] Player's favorite weapons
- [ ] Player's death place
- [ ] Weapon K/D rates
- [ ] Player's strategy in this game
- [ ] Etc.

