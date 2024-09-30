+++
title = 'Iterative Diagrams: A Scrabble Case Study'
date = 2024-09-29T18:46:29-04:00
draft = false
+++

## Motivation

When explaining board games to those unacquainted, I've often found the need for concise explainers separate from a rulebook. The goal is to broadly familiarize someone with what the game is rather than precisely how to play it.

I recently created one of these [explainers for the word association game *Codenames*](https://gillandsiphon.github.io/posts/codenames-primer/), and found that using Claude's Artifacts made iterative diagramming enjoyable.

I wanted to commentate on this kind of workflow, and so decided to do it again creating an explainer for *Scrabble*. This post documents my workflow in working with Claude 3.5 Sonnet and Artifacts for iterative diagramming. In this way, this post acts as an Appendix to the [*Scrabble* primer](https://gillandsiphon.github.io/posts/scrabble-case-study/) and [Claude Artifacts](https://gillandsiphon.github.io/posts/claude-artifacts/) posts.


# Diagramming a Scrabble Explainer

## Brainstorming

I know I need to communicate the basic premise of the game: players place letter tiles on a shared grid, spelling words to get points. I know that illustrating the grid and tiles is a straightforward visual that should show up early in the explainer. I'll start at this fuzzy idea.

### Initial Board

`Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board.`

!["scrabble1"](/img/scrabble1.png)

#### Observations:

* The standard Scrabble grid is 15x15, and Claude tried generating the grid in these dimensions too. However, seeing this, this may be too much complexity for an introductory graphic. I'm just hoping for readers to understand that letters are placed on a grid. 

* Claude attempts to color the premium squares. Performance deteriorates and the colors are not placed correctly.

* The tiles aren't positioned and don't look the way I anticipated, and don't really read as tiles.

### Simplified Board
> Reduce the size of the grid as this is a simplified representation. Remove the premium square colorings. Remove the tiles. Keep the middle square pink and add a black star overlaid and centered on it.

!["scrabble2"](/img/scrabble2.png)

It felt like a risk asking Claude to do four things at once, but it worked out okay. I like the simplified grid dimensions.

> Make the grid 9x9 and make the size a little larger. Set the board color to #F1DDC7. Set the pink color to #F59F9F. Replace the inner grid with a single gridline instead of double gridlines to simplify. Make sure the star is centered.

!["scrabble3"](/img/scrabble3.png)

Oops. Let's fix this.

> Please complete the grid. The lines on the right of the board aren't finished. It also looks like the rightmost outer border is thicker than the others.

!["scrabble4"](/img/scrabble4.png)

### Tiles

> Add 5 square #F1DDC7 tiles arranged in a row underneath the grid. The tiles each display one letter from the letters "R", "S", "T", "L", "E" in black.

!["scrabble5"](/img/scrabble5.png)

At this point, I run into problems several times asking Claude to add the tiles to the right side of the board, rotated and centered with respect to the board.

!["scrabble6"](/img/scrabble6-9.gif)


After several tries with no success, I start a new chat copy-pasting in the most recent working diagram to not hit usage limits due to long context length. I concede and ask for something simpler.

> Add tiles in a row "A C H T R"  to the top of the board too.  Rotate the tiles 180 degrees as this diagram depicts a top down view of the board. Make the tiles #d6b998.

!["scrabble11"](/img/scrabble11.png)

A good start! I have a feeling a few possible visuals can come from manipulating this base diagram.

### Letter Pool

Next, I'd like to represent the pouch or letter pool in some way and communicate to the reader that letters are randomly drawn and replenished.

A few ideas come to mind, some more doable in HTML and CSS than others, but the simplest seems to be rendering a bag or sack emoji to start. Using Lilian Weng's [emojisearch.app](https://www.emojisearch.app/), I find that the 'purse' emoji could do the job.

>Render a 👛, relatively medium to large to the right of the game board. 

!["scrabble12"](/img/scrabble12.png)

>Increase the black outer stroke on the tiles and game board significantly, and make them dark black.

!["scrabble13"](/img/scrabble13.png)

I notice that the right and bottom borders are either too thick or have redundant edges on them. I decide to go down a rabbit hole to fix this. If it doesn't work in three to five prompts, I should cut my losses.

!["scrabble13-16"](/img/scrabble13-16.gif)

It didn't work. I'm okay to move on from an earlier checkpoint. 

I'll take another risk and see if I can improve the representation of the purse emoji as the letter pool in a few prompts. Making minute changes starts to feel cumbersome as the length of the artifact grows.

!["scrabble18-26"](/img/scrabble18-26.gif)

### Placing Tiles

> Move the tiles "L" "E" "T" to vertically spell the word LET on the game board. Add a drop shadow under the tiles. The "E" should be placed on the center tile.

> I'm not sure what's going on with the other tiles. Revert all tiles aside from LET to their original positions and displays.

> Remove T L E from the bottom row. Remove drop shadow ONLY from the letters NOT on the board.

After some finagling, player tiles are moved to the board. 

> Now, place the second player's letters "T" and "H" preceding the "E" on the board horizontally. The "E" from "LET" will be used to spell "T H E", with the E being the rightmost element.

> Remove the H from the second player's row. It was just used in the word THE!

!["scrabble27-28"](/img/scrabble27-28.gif)

### Drawing Tiles

> Add an outer glow to the bag in #ffaa00. Add the tiles "A" "G" "M" to the lower row and add "M" "S" to the upper row. Add outer glow to the newly added tiles "A" "G" "M" "M" "S". Empty the bag.

A little bit of finagling again, and an imperfect but reasonable depiction of drawing tiles. Arrows would be nice, but based on previous toying around there's no chance they're going to work here. 

A quick note on finagling: rolling back to a previous iteration is made pretty painless by being able to edit previous prompts directly,  examining previous versions in the Artifacts display, and worst case, easily copying code and pasting it into a new chat.

!["scrabble29"](/img/scrabble29.png)

### Letter Points

>New diagram. Scale up three tiles. Add a small score on the bottom right, make the numbers different per letter.
> White background.

!["scrabble30"](/img/scrabble30.png)

Rolling back to a previous iteration is made pretty painless by being able to edit previous prompts directly,  examining previous versions in the Artifacts display, and worst case, easily copying code and pasting it into a new chat.

> Remove outer glow from tiles but keep the tiles. Remove outer glow from the bag. Put tiles back in bag, random letters.
> Add the accurate letter points to the bottom right of the tile for each letter.

!["scrabble31"](/img/scrabble31.png)

I don't blindly expect accuracy here, but it's a nice plus that they were all right.

A few failed efforts highlighting letters and displaying point totals. I'll concede, edit a previous prompt and try it in a simpler way.

> Outline L E T in the vertical "LET" in blue. In the same blue, add a rounded rectangle with "Point Total: 3" next to the bottom player's tiles.

> Do the same for T H E for the upper player and display the point total (upside down so it is visible to them).

> remove the bottom point total and the outline on L  and T.

In this case, the diagrams were adequate, but I didn't like the color. To save tokens, I just changed the color in the CSS manually.

!["scrabble33-34"](/img/scrabble33-34.gif)


### Premium Tiles

To introduce premium tiles, I'll remove unneeded elements.

> remove the bottom point total and the outline on L  and T.
> Remove the bag and the tiles in the bag.

I only want to gesture at the fact that there are marked squares on the board that are strategic to land on for point reasons. I'll choose to maintain the red diagonals, but not care too much about other cells aside from some semblance of symmetry and at least two gradations depending on what looks right.

> Color the diagonals of the grid square a slightly lighter red.

A little finagling and:

> Eight tasteful blue squares make an hexagon shape (spaced out) in the penultimate concentric square of the grid.

!["scrabble35"](/img/scrabble35.png)
