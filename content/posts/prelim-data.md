+++
title = '🚧 Casual Analysis of Crowdsourced Data for Clue Generation'
date = 2024-09-29T18:46:29-04:00
draft = false
weight = 1
+++

I am currently crowdsourcing data to evaluate model performance on a clue generation task. Details of the task are outlined in some detail [here](), but in short: I designed clue generation tasks and had five LLMs, as well as one human (me), generate clues for each task. I built and deployed a site that will present participants tasks and record participant guesses. The goal is to evaluate model clue-giving performance on this task.

!["word1"](/img/word1.png)

### Site

I deployed a site using Flask on PythonAnywhere. I used SQLite to store the results. As a blunt defense against vote manipulation, a uuid is assigned to each new user, stored in the Flask session.

!["word5"](/img/word5.png)


### Tasks 

As 10 problems are produced per model, the site serves one of 60 tasks randomly. The user has the option to skip to the next question, which will record the question as being incomplete unless completed later.

!["word2"](/img/word2.png)



