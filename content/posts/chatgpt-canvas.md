+++
title = '[DRAFT] Iterative Diagrams with Canvas: An Informal Exploration'
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

#### Prompt: 

> Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board.

ChatGPT begins streaming output, and a pane displaying HTML opens to fill the right-hand side of the screen. There is no option to toggle the Code for a rendered Preview at the moment. 

Like Artifacts, code is syntax highlighted, but canvas has line numbers. Most importantly, the displayed code is editable.

A small set of buttons in the bottom right allow me to select options to: add comments, add logs, fix bugs, port to a language, or code review.

There is no download button.

!["scraggle1"](/img/scraggle1.png)

#### Thoughts:

- This post isn't about model capabilities per se, but I'll still include my thoughts on the generated outputs: this output doesn't really grok the idea of a Scrabble explainer. The board is barren, and the tile placement suffers a bit from [The Monkey's Paw](https://gillandsiphon.github.io/posts/claude-artifacts/#the-monkeys-paw). 

> Represent the board as a grid. Put one set of tiles under the board and the other set of tiles on the right side of the board as if there are two players.

- A requested edit sends a cascading line-by-line highlight down the Canvas pane as changes are made line by line.

!["scraggle2"](/img/scraggle2.png)

> Make the board grid a square in dimension, 9x9 and with gridlines. 

> Add visible gridlines to the board.

- A few prompts don't result in reasonable changes. As Artifacts has versions, Canvas has arrows that can take you to a previous version of your code which you can choose to restore. 

- I think I'm just going to start over with less complex but more precise prompts.

> Generate a 7x7 beige grid with gridlines. The middle of the grid is colored a tasteful red.

- I forgot to ask for the background to be white. When I downloaded the HTML/CSS from Claude, rarely I did go into the file and change an element. Here, I'm able to do that right in the pane, which feels great.

!["scraggle4"](/img/scraggle4.png)

> Add a thick black outline on the grid. Add a black star in the center square overlaid on the red.

- Looks good. 

!["scraggle5"](/img/scraggle5.png)

- Tried to change the colors but it wouldn't work. I said I wouldn't really focus on model capabilities here, so I'm compartamentalizing this but: 4o capabilities feel more brittle than 3.5 Sonnet. 

- Toggling to previous versions feels okay, but since there's no visual preview, I have to scan the code to see what changed to determine if it's the right version. I think a highlight for what changed, or even a version number could help here!

> Add 5 square #F1DDC7 tiles arranged in a row underneath the grid. The tiles each display one letter from the letters “R”, “S”, “T”, “L”, “E” in black.

- I like the small text above the output that displays what actions 4o took. Things like "Made 2 edits", and "Added 5 comments".

- This was malformed and didn't render. I assume it's a bug, so I'll click the "Fix Bugs" button!

- Pretty sick, it fixes the bug! However, and maybe this is model capabilities again, the gridlines and center star cell are gone.

- After hitting, "Fix Bugs" again, things look okay.

!["scraggle9"](/img/scraggle9.png)

> Add tiles in a row “A C H T R” to the top of the board too. Rotate the tiles 180 degrees as this diagram depicts a top down view of the board. Make the tiles #d6b998.

- Won't render again. Issues, doesn't look like full code was output. I'll hit the "Code Review" button and see what happens.

    - Weird. I'm getting a "Failed to comment" action for a couple of seconds, and then a highlighting cascade. A few portions of the code remain highlighted and speech bubbles representing appliable suggestions appear. I don't believe the code was modified.

- Let me hit the "Fix Bugs" button. Sweet. It's fixed! 

!["scraggle10"](/img/scraggle10.png)

> Render a 👛, relatively medium to large to the right of the game board.

- Incomplete code. Not sure if this is a model capability thing or context length thing... Thank god for the "Fix Bugs" button though.

- Hitting "Fix Bugs". Fixed!

!["scraggle11"](/img/scraggle11.png)

> Increase the black outer stroke on the tiles and game board significantly, and make them dark black.

- I'm almost tempted to click "Fix Bugs" before even checking the output...

!["scraggle12"](/img/scraggle12.png)

- Oh. Another Monkey's Paw. I'll roll this back.

> Increase the black outer stroke on the tiles and game board slightly, and make them dark black. Increase the stroke on the tiles too.

- Hmm. No stroke on the tiles, but ok.

!["scraggle13"](/img/scraggle13.png)

- A few cosmetic changes.

!["scraggle14"](/img/scraggle14.png)

- I'm sensing a feeling of control, it's satisfying to use this.

### Pausing 

I'm going to pause this exercise here, as without the ability for Canvas to render elements, *and* disregarding model capability, I think I've seen most of what this interface offers with respect to this task. 

This exercise has also shown me how this interface seems to ideologically differ from Artifacts in terms of intended user behavior. 

I'll write up my takeaways in a more fleshed out piece.