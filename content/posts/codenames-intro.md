+++
title = 'A Simple Introduction to Codenames'
date = 2024-09-22T18:46:29-04:00
weigh = 1
draft = false
+++


The purpose of this article is to introduce the broad strokes of the party game *Codenames* as context for later posts.

## Basic Mechanics

*Codenames* is a word association game played with two competing teams headed by spymasters.

{{< figure src="/img/example22.png" caption="Codenames game setup with two teams and spymasters" alt="Codenames game board with word cards and players" >}}


### Board

25 random words are arranged in a 5x5 grid on the board. Each word has a hidden state visible only to the spymasters. 

{{< figure src="/img/example24.png" caption="Codenames game board with 25 word cards in a 5x5 grid" alt="5x5 grid of word cards for Codenames" >}}


### Turns

#### Clue-Giving

Each turn begins with a spymaster devising a one-word clue to hint their team towards guessing cards of their color on the board. The clue is accompanied with the number of intended cards being hinted.
!["test3"](/img/example25.png)

#### Guessing

The spymaster's team responds to the clue by guessing cards on the board they believe relate to the clue. Guessing ends if the team selects any card that is not their team's color.

!["test4"](/img/example21.png) 

### Assassin

One of the cards on the board has the hidden state "**Assassin**". If the assassin card is chosen, the game immediately ends, and the team that chose the card loses.

!["test5"](/img/example26.png)

### Win Condition

The game ends when all cards of one team's color have been revealed. Turns alternate until the win condition is reached.

!["test6"](/img/example27.png)
