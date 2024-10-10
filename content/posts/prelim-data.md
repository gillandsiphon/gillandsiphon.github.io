+++
title = 'Casual Analysis of Crowdsourced Data for Clue Generation'
date = 2024-10-08T18:46:29-04:00
draft = false
weight = 2
+++

I am currently crowdsourcing data to evaluate model performance on a clue generation task. Details of the task are outlined in some detail [here](https://gillandsiphon.github.io/posts/crowdsourcing-data/), but in short: I designed clue generation tasks and had five LLMs, as well as one human (me), generate clues for each task. I built and deployed a site that will present participants tasks and record participant guesses. The goal is to evaluate model clue-giving performance on this task.

!["word1"](/img/word1.png)

### Extremely Short Recap

The task is defined as generating a clueword which relates two target words but not two other words (see Figures or see [here](https://gillandsiphon.github.io/posts/crowdsourcing-data/) for detail). This exercise tests the performance of gpt-3.5, gpt-4o, o1-mini, o1-preview, llama-405b-turbo-instruct, and human performance on this task.

10 problems are produced per model, and deployed on a site which serves one of the 60 tasks randomly. The user has the option to skip to the next question.

!["word2"](/img/word2.png)


### Site

I deployed a site using Flask on PythonAnywhere. I used SQLite to store the results. As a blunt defense against vote manipulation, a uuid is assigned to each new user, stored in the Flask session.

### Recruiting

I solicited answers to these tasks by posting to various online spaces: Reddit, X, and Discord communities. Additionally, I recruited two of my friends to complete all 60 questions.

It's difficult to make judgements based on this population, but here are some stray thoughts on this I'm processing:

— The two friends I recruited are familiar with the word association game [Codenames](https://gillandsiphon.github.io/posts/codenames-primer/), and I would believe them to have stellar performance on this task. 

- The majority of online spaces were machine learning related spaces.


### Data

After some basic processing to isolate valid data, I have **450** task instances recorded, across 44 unique users. 

Most users answered a single-digit amount of questions (median 7). Although in some experimental designs it may make sense to discard unique users that do not meet some threshold, I think in this case, task instances from users who answered a low amount of questions are still meaningful.

{{< figure src="/img/word6.PNG" caption="I recruited two friends to answer all 60 questions, explaining those outliers." >}}

### Incomplete Questions

Incomplete questions, where participants chose one correct choice and passed or left the session were dropped, leaving **435** unique task instances.

## Model Performance

Preliminary results are in. A few surprises here:

- o1-mini outperforms o1-preview
- gpt-3.5 outperforms gpt-4o
- is it a surprise that o1 outperforms me?

!["word8"](/img/word8.png)
