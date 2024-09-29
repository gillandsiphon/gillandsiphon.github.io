+++
title = 'Claude Artifacts for Iterative Diagramming'
date = 2024-09-28T18:46:29-04:00
weight = 2
draft = false
+++

## Working on a Visual Explainer

I recently used Claude to help me write a blog post I've been planning for a while and found iterative diagramming promising and enjoyable.

The post I wrote is [a short primer for the word association game *Codenames*](../codenames-primer/). I've often found the need for a concise explainer that's separate from a rulebook—the goal is to familiarize someone with what *Codenames* is rather than precisely how to play it.

As *Codenames* is a visual game with color-coded cards and hidden information, representing concepts with diagrams is a natural choice. 

{{< figure src="/img/example13.png" caption="Figure 1. An example diagram that was left on the cutting room floor." alt="Codenames game diagram" >}}

## Thoughts on Artifacts

In my experience, image editing software for creating diagrams like these works best when you've finished brainstorming and have a clear vision. It's possible to brainstorm and make adjustments during the creation process, but as the complexity of the diagrams grows, it becomes costly to try out new ideas. 

Models like Claude act as something between a [rubber duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) and an immediate feedback loop. I've found they facilitate the brainstorming process, maybe even mostly by forcing the user to articulate their vision, and potentially offer immediate feedback that makes taking a further step actionable.

Anthropic's [Artifacts](https://www.anthropic.com/news/artifacts) really tightens the immediate feedback loop by rendering the, for example, HTML/CSS in a dedicated window alongside the text chat. You see output *as* you brainstorm, and I found it promising to land on a viable design for an instructional diagram working iteratively with Claude.  

### Workflow and Limitations by Example

#### Scrabble

To demonstrate a workflow, let's work through a toy example of generating diagrams for a *Scrabble* explainer. The objective of the explainer would be to help the reader understand what *Scrabble* *is* and touch on the core mechanics. 

Take a look at the [official rules](https://www.hasbro.com/common/instruct/Scrabble_(2003).pdf). While a document like this is a comprehensive ruleset, it's too dense to act as a skimmable summary of the game.

#### Brainstorming

I know I need to communicate the basic premise of the game: players place letter tiles on a shared grid, spelling words to get points. I know that illustrating the grid and tiles is a straightforward visual that should show up early in the explainer. I'll start at this fuzzy idea.

> Prompt: Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board.

!["scrabble1"](/img/scrabble1.png)

Alright, this is interesting. A few things to note:

* The standard Scrabble grid is 15x15, and Claude tried generating the grid in these dimensions too. However, seeing this, this may be too much complexity for an introductory graphic. I'm just hoping for readers to understand that letters are placed on a grid. 

* Claude attempts to color the premium squares. Performance deteriorates and the colors are not placed correctly.

* The tiles aren't positioned and don't look the way I anticipated, and don't really read as tiles.

> Prompt: Reduce the size of the grid as this is a simplified representation. Remove the premium square colorings. Remove the tiles. Keep the middle square pink and add a black star overlaid and centered on it.

!["scrabble2"](/img/scrabble2.png)

* It felt like a risk asking Claude to do four things at once, but it worked out okay.

* I like the simplified grid dimensions.

> Prompt: Make the grid 9x9 and make the size a little larger. Set the board color to #F1DDC7. Set the pink color to #F59F9F. Replace the inner grid with a single gridline instead of double gridlines to simplify. Make sure the star is centered.

!["scrabble3"](/img/scrabble3.png)

Oops. Let's fix this.

> Please complete the grid. The lines on the right of the board aren't finished. It also looks like the rightmost outer border is thicker than the others.

!["scrabble4"](/img/scrabble4.png)

> Add 5 square #F1DDC7 tiles arranged in a row underneath the grid. The tiles each display one letter from the letters "R", "S", "T", "L", "E" in black.

!["scrabble5"](/img/scrabble5.png)

At this point, I run into problems a few times asking Claude to add the tiles to the right side of the board, rotated and centered with respect to the board.

!["scrabble6"](/img/scrabble6.png)
!["scrabble7"](/img/scrabble7.png)
!["scrabble8"](/img/scrabble8.png)
!["scrabble9"](/img/scrabble9.png)

After several tries with no success, I start a new chat copy-pasting in the most recent working diagram to not hit usage limits due to long context length. I concede and ask for something simpler.

> Add tiles in a row "A C H T R"  to the top of the board too.  Rotate the tiles 180 degrees as this diagram depicts a top down view of the board.




