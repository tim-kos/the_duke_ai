# The Duke AI

This is the repo revival of my Age of Empires 2 AI computer player.

* It can play any game mode, civilization, map, difficulty and team setup.
* It only cheats on the "Hardest" difficulty to provide some additional difficulty for expert players.
* It features several strategies, from Feudal age rushes, Knight rushes in early castle age, Eagle man rush, economic booming, etc. It chooses strategies randomly, but has preferences of course depending on the map and team setup.

Feedback is welcome!

## Installation

Please put all files with a *.per or an *.ai extension in your AI folder, but please let they stay in there folders.
All the new taunts that you'll find in the folder "The Duke-AI - media" do you put into your taunt directory.

If you did this you would have to start a new game and you must choose "The Duke-AI" as the player. Then you can play with that AI.

## Boar cheating

The AI gets some wood after 5min (amount of wood is dependant on the difficulty level), because the AI cannot hunt boar (due to the buggy game engine) and that's why
a human player can advance to feudal age earlier and pretty stronger than an AI. To remove boar cheating, please go into the Main Files folder and open boar_cheating.per with a text editor. There you find this:


```
#load-if-not-defined DIFFICULTY-MODERATE
#load-if-not-defined DIFFICULTY-HARD
#load-if-not-defined DIFFICULTY-HARDEST
;***********************************************
;***********************************************

(defrule        ;if
  (true)            ;this condition is always true -> the rule always gets executed
=>          ;then
  (set-goal BOAR-CHEATING NO)     ;LINE X !! ;the AI sets goal BOAR-CHEATING to NO (constant)
  (disable-self)          ;only initialisation
)

;***********************************************
;***********************************************
#end-if
#end-if
#end-if



#load-if-not-defined DIFFICULTY-EASIEST
#load-if-not-defined DIFFICULTY-EASY
;***********************************************
;***********************************************

(defrule        ;if
  (true)            ;this condition is always true -> the rule always gets executed
=>          ;then
  (set-goal BOAR-CHEATING YES)      ;LINE Y !! ;the AI sets goal BOAR-CHEATING to YES (constant)
  (disable-self)          ;only initialisation
)

;***********************************************
;***********************************************
#end-if
#end-if
```


If you want the AI to have boar cheating on easiest-, easy- or moderate-difficulty then please change the "NO" into a "YES" in line x (use capital letters, otherwise the game will give an error message).
If you want the AI not to have boar cheating on hard- or hardest-difficulty, then change the second "YES" in line y into a "NO".

## Taunts

Put all taunts from the "The Duke-AI Media"-folder into your "taunt"-folder in your Age of Empires II folder.

Here is a list of all taunts the Duke-AI can react to. Only allied Duke-AIs can react to taunts. If you send a taunt to a neutral or enemy player he will let you know that you cannot command him.

Press enter and send the number (listed below) to your allies. Make sure you are really chatting with the desired player based on your settings.

For example: Press enter and write 51. This will cause your ally duke to cheat some resources.

* 31  The AI will launch an attack, or if it won’t, it will tell you the reason.
* 32  The AI ceases creating extra villagers.
* 33  The AI creates extra villagers.
* 34  The AI will build a navy.
* 35  The AI will stop building a navy.
* 36  The AI will only attack when you give a sign.
* 37  The AI will try to build a wonder.
* 38  The AI will give you its spared resources.
* 42  The AI will tell you to which age it is.
* 47  The AI will try to advance to the next age.
* 48  The AI will build more forward buildings and will attack more frequently.
* 49  It won’t build any forward-buildings anymore and will be very passive.
* 50  The AI stops cheating.
* 51  The AI enables cheating resources (all resources!).
* 52  The AI will only cheat food.
* 53  The AI will only cheat wood.
* 54  The AI will only cheat gold.
* 55  The AI will only cheat stone.
* 56  The AI will primary train infantry (swordsmen + spearmen).
* 57  The AI will primary train swordsmen.
* 58  The AI will primary train spearmen.
* 59  The AI will primary train archers.
* 60  The AI will primary train skirmishers.
* 61  The AI will primary train cavalry-archers.
* 62  The AI will primary train light cavalry.
* 63  The AI will primary train knights.
* 64  The AI will primary train camels.
* 65  The AI will primary train its unque-unit.
* 66  The AI will secondary train infantry (swordsmen + spearmen).
* 67  The AI will secondary train swordsmen.
* 68  The AI will secondary train spearmen.
* 69  The AI will secondary train archers.
* 70  The AI will secondary train skirmishers.
* 71  The AI will secondary train cavalry-archers.
* 72  The AI will secondary train light cavalry.
* 73  The AI will secondary train knights.
* 74  The AI will secondary train camels.
* 75  The AI will secondary train its unique unit.
* 76  The AI’s primary combat siege unit is the ram.
* 77  The AI’s primary combat siege unit is the mangonel.
* 78  The AI’s primary combat siege unit is the scorpion.
* 79  The AI’s primary combat siege unit is the bombard-cannon.
* 80  The AI’s primary combat siege unit is the trebuchet.
* 81  The AI’s secondary combat siege unit is the ram.
* 82  The AI’s secondary combat siege unit is the mangonel.
* 83  The AI’s secondary combat siege unit is the scorpion.
* 84  The AI’s secondary combat siege unit is the bombard-cannon.
* 85  The AI’s secondary combat siege unit is the trebuchet.
* 86  The AI will scatter its units when it attacks.
* 87  The AI will group its units when it attacks.

## Supported difficulties

Easiest: something like a whole newbie! I think everybody who has never seen a computer yet is able to win!

Easy: a bit better than easiest, but every Age of Empires newbie should be able to win!

Moderate: you play against a well practised player! This should be fun, but on hard or hardest you can enjoy many more tricks, rushes and strategies of The Duke-AI!

Hard, Hardest: these are the most challenging difficulty levels of The Duke-AI (as they should be :)). Here, there are rushes, optimised building strategies.. just most changelling.
The only difference between hard and hardest, is that in hardest goes everything faster and earlier and the rushes are more difficult to defend.
If hardest is too easy for you, then play against 2 or 3 or even more The Duke-AIs, but I think a 2 vs 2 cheating The Dukes on hardest should be hard enough! By the way, on hardest the duke cheats a little bit. On hard the duke does not cheat.

The Duke-AI can take on 3 standard computer opponents which are teamed together (not always, but often) and in one test it could beat phoenixknight and often beats alliance-AI by Dr. Mabuse.
