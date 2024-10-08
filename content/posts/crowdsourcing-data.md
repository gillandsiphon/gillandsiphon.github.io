+++
title = 'Crowdsourcing Data for a Clue Generation Task'
date = 2024-09-29T18:46:29-04:00
draft = false
weight = 1
+++

This toy problem has two objectives: to act as an exercise for crowdsourcing data [(here!)](https://gillandsiphon.pythonanywhere.com/.
)), and to evaluate model performance on a word association task.

### Task Definition

To start exploring how models perform on a word association problem (clue generation), I've defined a simple task: 

!["word1"](/img/word1.png)

> **Task**: Given two target words and two other words, generate a clue that relates to the two target words but does not relate to the two other words.

This task bears resemblance to the [Remote Associates Test]("https://www.remote-associates-test.com/") and the [NYT game Connections](https://www.nytimes.com/games/connections), and is a subproblem of the word association game [*Codenames*](https://gillandsiphon.github.io/posts/codenames-primer/). 


### Generating Tasks

To generate the tasks, I use the [wordlist from *Codenames*](https://github.com/Gullesnuffs/Codenames/blob/master/wordlist-eng.txt) to randomly generate 2x2 board grids, as the wordlist has properties (such as generally, polysemanticity) I wish to retain for this evaluation. I then randomly assign two of the words to be target words.

I generated 10 of these problems.

{{< figure src="/img/word2.png" caption="One formulation of the task with correct answers revealed." >}}

#### Models

I evaluate GPT-3.5, GPT-4o, o1-mini, o1-preview, and Llama-405b-turbo-instruct in this experiment.

### Generating Clues with Models

Each model was given the following prompt and asked to generate a clue, and reasoning:

```
You are an AI assistant specialized in generating clues for the game Codenames. Your task is to create a single-word clue that connects two target words while avoiding any connection to other words on the board.

#### Prompt: 

Game Context:
- Codenames is a word-guessing game where players give one-word clues to help their teammates identify specific words on a board.
- The ideal clue relates strongly to the target words but not to any other words, to avoid confusion.

Board Setup:
- All board words: {', '.join(words)}
- Target words: {', '.join(targets)}
- Words to avoid: {', '.join(non_targets)}

Instructions:
1. Analyze the semantic (and otherwise) relationships between the target words.
2. Consider potential clues that connect both target words.
3. Evaluate each potential clue to ensure it doesn't relate to the words to avoid.
4. Choose the best clue that maximizes connection to targets and minimizes connection to other words.

Your response must follow this exact format:
Clue: [your one-word clue]
Explanation: [brief explanation of how the clue relates to the target words and why it's a good choice]

Examples:
1. Board words: BEACH, MOON, WHALE, DESERT
    Target words: BEACH, WHALE
    Clue: Ocean
    Explanation: "Ocean" relates to both beach (there's an ocean nearby), and whale (live in the ocean) without being related to desert or moon strongly. They may relate via biome and tide, but beach and whale would be first choices. 

2. Board words: PIANO, DOCTOR, SCHOOL, ROCK
    Target words: PIANO, ROCK
    Clue: Ivory
    Explanation: "Ivory" relates to piano and rock as it is used in pianos and a kind of rock-like material. "Ivory" does not relate to doctor or school. 

3. Board words: SPIDER, LETTER, WEB, KEYBOARD
    Target words: SPIDER, WEB
    Clue: Silkworm
    Explanation: "Silkworm" relates to both spider and web as it is an insect that generates a silk lattice, kind of like a web. Letter and keyboard don't relate.

Remember, the quality of the clue is crucial. Take your time to think through the options carefully before providing your answer for the given board setup.
```

I didn't use structured output, and instead manually populated the database with the model's generated clue. The reasoning was discarded, but remains as an interesting artifact for future inspection.

#### Human Clue

I also wanted to evaluate model performance against human performance. For each board state, I generated a clue for the two target words and gave myself a limit of 90 seconds per clue. 

#### Crowdsourcing

I set up a site using Flask and SQLite to randomly sample from the pool of problems. PythonAnywhere made it free and easy to deploy and start collecting data.

Evaluation is currently underway at https://gillandsiphon.pythonanywhere.com/.

