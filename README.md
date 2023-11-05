# Minesweeper SFML
**Minesweeper💣game using SFML - c++**

This is an implementation for the famous game Minesweeper using backtracking algoritm
# Setup sfml on your VS 👨🏼‍💻
You can see this video ▶️ here(Add the audio libraries also if you want to use it) :
https://www.youtube.com/watch?v=9fn45eLaApM

And for vs code you can see this one :
https://www.youtube.com/watch?v=rZE700aaT5I

or the SFML official website :
https://www.sfml-dev.org/ 
# The game
My project was mainly about 2D arrays (The grid 𝄜 ) and using the backtracking 🔙 algorithm (finding the empty cells)

The famous game Minesweeper 💣 is basically trying to find mines without pressing on them as the numbers 🔢 determine the number of mines in the surrounding 8 blocks as we see in this image

![R](https://github.com/Kidzantso/Minesweeper-SFML/assets/116034195/00ffeb3d-1d5e-41c7-9ba4-41bb2b89cbd9)

And when you press on an empty cell it shows all the surrounding empty ones

![Minesweeper](https://github.com/Kidzantso/Minesweeper-SFML/assets/116034195/30855584-3a1c-45bd-9d8a-52141850eefc)

And you try to exclude the suspicious blocks and know exactly where the mines are and flag them to win the game 🏆

# Methodology
## Start 🚦
First we have 3 grids
1. Interface for the user
2. The original grid
3. Flagging grid

The first grid can run through diffrent steps which are
* All cells are closed
* Pressing to Open cells
* Pressing to Flag cells

We read the image named tiles and according to the state of the second grid we put a sprite from the image

* 0 = Opened cell
* 1-8 = The numbers of mines arround
* 9 = Mine
* 10 = Closed cell
* 11 = Flag

The second grid is the one made for the game logic which contains the numbers and the mines, at first we randomize the places of the mines and put it as number 10 and then we put the numbers according to the number of mines around

The third grid determines if the cells are open or closed so we can flag them and for checking if the game is over or not
## Playing 🕹️
You start by pressing a random closed tile and when you press it the cell is opened and we read the second grid to check the number in this tile and according to it we update the first grid by the sprites from the image

If there is a number we display it only without opening any more cells 

But if it is an empty cell We check the surrounding tiles, if they are empty we open them also. For this we use the backtracking function : 
1. We search in the surrounding cells if we reached the end of the grid OR we reached a number
2. If no we open them and search again in THEIR (the new opened ones) surrounding cells and repeat step one
3. If yes we stop and return to the previous cell opened until we return to the original opened cell and we open them all

If we pressed the right click on the mouse we check if the cell is not opened before we flag it

## Ending 🏁
We check if the number of not opened cells are equal to 10 (The number of mines) we display victory 🏆 , else if we opened a mine we display game over 👾 and the game ends
## Controls 🎮
* Enter : Restart 🔄
* Right click : Flag ⛿ 
* Left click : Open 🔓

# The game view

![Screenshot 2023-11-05 225753](https://github.com/Kidzantso/Minesweeper-SFML/assets/116034195/18621e76-a067-4ea7-8732-132b9ede3452)

# Alexander
As you can see there is this smiley face in the bottom of the screen 

He is called Alexander (Stole the name from Kofybrek, Yes i know) and we determine his state according to the game
* Happy
* Sad
* Waiting
* Sacred
And we change his state according to the actions we are tacking

1. If you win he is happy 😎
2. If you lost he becmoes sad ☹
3. Scared when you are pressing blocks 😨
4. His initial state is waiting 🙄

# References 📖
The text function, Alexander and the steps taken in the project and understanding SFML this awesome man : https://www.youtube.com/@Kofybrek

The Startup code('ve added ALOT in it) : https://www.youtube.com/watch?v=c8wswUEfnrQ

The backtracking code is written from scratch from diffrent references but you can easily understand it from geeks for geeks or w3schools

# Notes 📋
If you want to remove the sounds just remove the sounds variables (sound buffers and sounds lines : 179-180) from the code in the functions'variables and in the main lines : remove lines 42-46,70-84,remove the variables(SoundBuffer& b2,Sound& s2,int &count)line 59,remove soundscount(line 160) from the main,and finally remove lines 234-238,249-253

You can add a function to prevent losing from the first time from kofybrek's video there is a small bug that only displays 2 or 3 mines but i'll work on it soon after finishing some projects

Don't hesistate to send me any updates on the code or ask for help if you didn't understand any line in the code 
