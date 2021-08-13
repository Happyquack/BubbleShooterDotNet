# BubbleShooterDotNet
A revision of a classic

## Purpose

This project is essentially an effort to not only have a standalone version of [bubble shooter dot net](https://www.bubbleshooter.net), but to also improve upon it, mainly in efficiency. 

Perks of a standalone edition are that advertisements or other games cannot accidentally be clicked on, the game can be accessed offline (if in application form), and portability/synergy with LiveSplit.

Improvements are, but not limited to:
- Faster runtime
- Better graphics
- Fleshing out of unfinished/abandoned features
- In-game timer
- An easy visual indication of how many colors are eliminated
- An "easy mode" that shows projected path of the ball
- Toggling of number of colors or board size

It is unclear whether or not this project will be coded in Java or JavaScript.

## Planning notes

Known mechanics of Bubble Shooter Dot Net:
- There are bubbles of 6 different colors.
- The screen starts with 9 rows of 17 (randomly chosen?) balls, which are offset to fit together in the gaps of other rows.
- The "shooter" shoots balls with colors randomly chosen from the list of colors still on the board, from the center of the bottom of the row (exact position yet to be determined) to the direction of the mouse. Balls bounce off of walls.
- At any given time, the shooter has a "current" ball, and an "upcoming" ball. The upcoming ball becomes the current ball after the previous current ball's effects have been evaluated, and the color of the next upcoming ball is then chosen.
- It is important to note here that when the board is devoid of a certain color, that color no longer shows up in the shooter's queue. This can be subverted if the "next" ball is of the color that is about to be eliminated.
- Every time a bubble is shot and connects with a chain of two or more of its color, the entire chain is eliminated.
- Any group of balls not connected to the top of the screen are automatically eliminated.
- Any time a bubble is shot that doesn't result in eliminations, a "foul" is used up.
- When a foul is to be used up but there are none, the player regains n - 1 fouls, where n was the number of fouls the player last recieved. If n = 1, then the player recieves x - 1 fouls, were x is the number of colors remaining.
- When a foul is to be used up but there are none, all of the balls on the screen are moved down 1 (algorithm as of yet unknown) row, and a new row of randomly chosen balls is added to the top of the screen.
- The entire board is 15 rows tall. When a ball must be placed below this 15th row, the game ends.
- When the entire board is devoid of balls, the game is won and the final score is the current score multiplied by 2.
- (SCORING SYSTEM UNKNOWN)
