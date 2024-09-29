+++
title = 'Claude Artifacts for Iterative Diagramming'
date = 2024-09-28T18:46:29-04:00
weight = 2
draft = false
+++

## Working on a Visual Explainer

I recently used Claude to help me write a blog post I've been planning for a while and found iterative diagramming productive and enjoyable.

The post I wrote is [a short primer for the word association game *Codenames*](../codenames-primer/). I've often found the need for a concise explainer that's separate from a rulebook—the goal is to familiarize someone with what *Codenames* is rather than precisely how to play it.

As *Codenames* is a visual game with color-coded cards and hidden information, representing concepts with diagrams is a natural choice. 

{{< figure src="/img/example13.png" caption="Figure 1. An example diagram that was left on the cutting room floor." alt="Codenames game diagram" >}}

## Thoughts on Artifacts

In my experience, image editing software for creating diagrams like these works best when you've finished brainstorming and have a clear vision. It's possible to brainstorm and make adjustments during the creation process, but as the complexity of the diagrams grows, it becomes costly to try out new ideas. 

Models like Claude act as something between a [rubber duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) and an immediate feedback loop. I've found they facilitate the brainstorming process, maybe even mostly by forcing the user to articulate their vision, and potentially offer immediate feedback that makes taking a further step actionable.

Anthropic's [Artifacts](https://www.anthropic.com/news/artifacts) really tightens the immediate feedback loop by rendering the, for example, HTML/CSS in a dedicated window alongside the text chat. You see output *as* you brainstorm, and I found it easy to land on a viable design for an instructional diagram working iteratively with Claude.  

### Workflow and Limitations by Example

#### Scrabble

To demonstrate a workflow, let's work through a toy example of generating diagrams for a *Scrabble* explainer. The objective of this document is to help the reader understand what *Scrabble* *is* and touch on the core mechanics. 

Take a look at the [official rules](https://www.hasbro.com/common/instruct/Scrabble_(2003).pdf). While a document like this is a comprehensive ruleset, it's too dense to act as a skimmable summary of the game.

#### Brainstorming

I know I need to communicate the basic premise of the game: players place letter tiles on a shared grid, spelling words to get points. I know that illustrating the grid and tiles is a straightforward visual that should show up early in the explainer. I'll start at this fuzzy idea.

> Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board.

!["scrabble1"](/img/scrabble1.png)





