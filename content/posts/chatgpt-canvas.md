+++
title = 'ChatGPT Canvas vs. Claude Artifacts'
date = 2024-10-03T17:00:00-04:00
draft = false
weight = 3
+++

### Canvas

OpenAI launched Canvas today, a new ChatGPT interface that's aimed at collaborative, iterative tasks. Promotional material showcases how Canvas opens a dedicated panel for documents. A few shortcuts focused on (for now) code and writing allow for quick changes like porting programming languages or fixing bugs. Changes can be made line by line, and suggestions can be generated and suggested in the UI.

### Scrabble Explainer

I recently used Claude Artifacts to help me create explanatory diagrams for [*Scrabble*](https://gillandsiphon.github.io/posts/scrabble-primer/) as I found the original rules too long for a first introduction.

I posted my [Artifacts takeaways](https://gillandsiphon.github.io/posts/claude-artifacts/), and [chronicled my workflow](https://gillandsiphon.github.io/posts/scrabble-case-study/). 

In this post, I want to explore Canvas through this task of iterative diagramming. As of today, ChatGPT Canvas does not render a visual display in the Canvas pane, so I will be rendering the generated HTML/CSS separately. In that way, this will not be a precisely fair comparison, but I'll do my best to stay impartial of that and report my findings on how Canvas and Artifacts differ. I'll also try to decouple model capability from this exploration of the interface.

### Start

I'll start at the same place I started for the scrabble explainer.

> Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board.

ChatGPT begins streaming output, and a pane displaying HTML opens to fill the right-hand side of the screen. There is no option to toggle the Code for a rendered Preview at the moment. 

Like Artifacts, code is syntax highlighted, but canvas has line numbers. Most importantly, the displayed code is editable.

A small set of buttons in the bottom right allow me to select options to: add comments, add logs, fix bugs, port to a language, or code review.

There is no download button.

!["scraggle1"](/img/scraggle1.png)
