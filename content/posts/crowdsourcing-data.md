+++
title = 'Crowdsourcing Data for a Word Association Task'
date = 2024-09-29T18:46:29-04:00
draft = false
weight = 1
+++

### Task Definition

To start exploring how models perform on a word association problem, I've defined a simple task: 

!["word1"](/img/word1.png)

> **Task**: Given a clueword and four board words, select the two target words of the four board words that relate to the clue. Selections are made one word at a time. The task ends when either an unrelated word is selected, or both target words are chosen.

### Generating Tasks

This task is a simple version of a more complex problem, and a subproblem of the word association game [*Codenames*](https://gillandsiphon.github.io/posts/codenames-primer/). 

To generate the tasks, I use the [wordlist from *Codenames*](https://github.com/Gullesnuffs/Codenames/blob/master/wordlist-eng.txt), as it has properties (such as generally, polysemanticity) I wish to retain for this evaluation. 