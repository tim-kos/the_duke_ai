# The Duke AI

This is the repo revival of my Age of Empires 2 AI computer player.

* It can play any game mode, civilization, map, difficulty and team setup.
* It only cheats on the "Hardest" difficulty to provide some additional difficulty for expert players.
* It features several strategies, from Feudal age rushes, Knight rushes in early castle age, Eagle man rush, economic booming, etc. It chooses strategies randomly, but has preferences of course depending on the map and team setup.

Feedback is welcome!


* Installation

Please put all files with a *.per or an *.ai extension in your AI folder, but please let they stay in there folders.
All the new taunts that you'll find in the folder "The Duke-AI - media" do you put into your taunt directory.

If you did this you would have to start a new game and you must choose "The Duke-AI" as the player. Then you can play with that AI.



* Boar cheating

The AI gets some wood after 5min (amount of wood is dependant on the difficulty level), because the AI cannot hunt boar (due to the buggy game engine) and that's why
a human player can advance to feudal age earlier and pretty stronger than an AI. To remove boar cheating, please go into the Main Files folder and open The Duke Boar Cheating.per with a text editor. There you find this:


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



* Taunts

Please check "The Duke-AI supported taunts.doc" to have a list of all taunts supported by the AI. It would be helpful if you would print that list.

Put all taunts from the "The Duke-AI Media"-folder into your "taunt"-folder under your Age of Empires II folder.



* Supported difficulties

Easiest: something like a whole newbie! I think everybody who has never seen a computer yet is able to win!

Easy: a bit better than easiest, but every Age of Empires newbie should be able to win!

Moderate: you play against a well practised player! This should be fun, but on hard or hardest you can enjoy many more tricks, rushes and strategies of The Duke-AI!

Hard, Hardest: these are the most challenging difficulty levels of The Duke-AI (as they should be :)). Here, there are rushes, optimised building strategies.. just most changelling.
The only difference between hard and hardest, is that in hardest goes everything faster and earlier and the rushes are more difficult to defend.
If hardest is too easy for you, then play against 2 or 3 or even more The Duke-AIs, but I think a 2 vs 2 cheating The Dukes on hardest should be hard enough! By the way, on hardest the duke cheats a little bit. On hard the duke does not cheat.

The Duke-AI can take on 3 standard computer opponents which are teamed together (not always, but often) and in one test it could beat phoenixknight and often beats alliance-AI by Dr. Mabuse.
