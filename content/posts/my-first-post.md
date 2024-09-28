+++
title = 'An Introduction to Codenames'
date = 2024-09-22T18:46:29-04:00
draft = false
+++

 ![Red Team target words "Apple" and "Orange"](/img/example1.png)

The purpose of this article is to introduce the party game *Codenames* extremely simply, in order to seed the backdrop for a later discussion on *Codenames* as a means to evaluate model reasoning, planning, and misdirection. 
### Basic Mechanics

*Codenames* is a word association game played with two competing teams headed by spymasters. !["test"](/img/example22.png)
25 random words are arranged in a 5x5 grid on the board. Each word has a hidden state visible only to the spymasters. 
!["test2"](/img/example24.png)

Each turn begins with a spymaster devising a one-word clue to hint their team towards guessing cards of their color on the board. The clue is accompanied with the number of intended cards being hinted.
!["test3"](/img/example25.png)
The spymaster's team responds to the clue by guessing cards on the board they believe relate to the clue. 

!["test4"](/img/example21.png) Guessing ends if the team selects any card that is not their team's color. 

!["test5"](/img/example13.png)

One of the cards on the board has the hidden state "**Assassin**". If the assassin card is chosen, the game immediately ends, and the team that chose the card loses.