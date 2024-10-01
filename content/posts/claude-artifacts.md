+++
title = 'Claude Artifacts for Iterative Diagramming'
date = 2024-09-28T18:46:29-04:00
draft = false
+++

# Explainer Diagrams

I recently used Claude and Artifacts to help me create explanatory diagrams for the board games [*Codenames*](https://gillandsiphon.github.io/posts/codenames-primer/) and [*Scrabble*](https://gillandsiphon.github.io/posts/scrabble-primer/) as I found the original rules too long for a first introduction.

In doing so, I found iterative diagramming with Claude and Artifacts enjoyable. In this post, I want to organize my takeaways. I've also recorded my workflow in an [appendix post](https://gillandsiphon.github.io/posts/scrabble-case-study/).

{{< figure src="/img/review3.png" caption="Examples of diagrams from the *Codenames* and *Scrabble* explainers." >}}


# Artifacts
 
Models like Claude act as something between a [rubber duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) and an immediate feedback loop. I've found they facilitate the brainstorming process if only by forcing the user to articulate their vision. Model UIs can also surface immediate feedback that makes taking a further step actionable.

Anthropic's [Artifacts](https://www.anthropic.com/news/artifacts) really tightens the immediate feedback loop by rendering the, for example, HTML/CSS in a dedicated window alongside the text chat. You see output *as* you brainstorm, and I found it promising to land on a viable design for an instructional diagram working iteratively with Claude.  


## Strengths


### Immediate Feedback

Working with models like Claude in a text-only UI, like the one that serves ChatGPT and most other large models, is a workflow that's technically just as capable at writing HTML and CSS.

However, Anthropic's [Artifacts](https://support.anthropic.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them) feature, which displays content like renderable code or text documents in a dedicated panel, provides immediate feedback by rendering output without occluding the text chat.

Anthropic's [How we built Artifacts](https://www.youtube.com/watch?v=vUdNaAAc4FY) video outlines the way a feedback loop would work without Artifacts: you'd have to copy-paste the output code into an editor, render it or run it, and then alt-tab back to the chat window to do it again. 

Artifacts tightens that feedback loop and makes iterating enjoyable.

### Create As You Brainstorm

Working iteratively with Claude has a kind of lightness. You can start brainstorming without an immediately clear vision, just thumbing at the clay until viable shapes surface. 

Working on the [Scrabble Explainer](https://gillandsiphon.github.io/posts/scrabble-case-study/#brainstorming), I knew I wanted diagrams that simplify components of Scrabble. Without much more of a plan, it became more clear to me *what I wanted* by being shown the things I didn't want.

### Branching

Sometimes chasing a hunch doesn't work out. I ran into several instances of ideas that didn't fully pan out. Artifacts, and the rest of the UI make it easy to backtrack and continue despite hiccups. 

#### Retry
A prominent Retry button at the bottom of each output is an easy way to reroll if you want to see another variation, or potentially correct an error.

!["review4"](/img/review4.png)

#### Versions
To visually refer to previous artifacts, a Version history is kept within chat, displayed on the bottom of the Artifacts panel. 

!["review5"](/img/review5.png)

#### Edit
Processed prompts can be edited to continue from a "checkpoint" in the chat instance. I found this the most helpful when I accidentally flubbed the prompt or completely abandoned a rabbithole I was heading down.

!["review6"](/img/review6.png)

#### New Chat
If all else fails, code blocks in the text chat and Artifacts pane can be copied with a copy button, and pasted into a new chat instance.


### Delightful Surprises

#### Vibe Reading

Although I find being extremely precise is the right way to approach asking for iterative changes, especially those that involve rearrangements, reorientations or other element transformations, it is delightful when you lob an unclarified
ask and Claude hits it out of the park.

It felt satisfying receiving fitting outputs even when prompting Claude with fuzzy descriptors like "medium to large" or "significantly".

{{< figure src="/img/scrabble12.png" caption="Prompt: Render a 👛, relatively medium to large to the right of the game board." >}}

{{< figure src="/img/scrabble13.png" caption="Prompt: Increase the black outer stroke on the tiles." >}}

#### Spellcasting
>Note: The vision input modality was not used in this or associated exercises. 

This exercise made visceral the importance of word choice while prompting.  

Sometimes you'll want to request something that you may not have really verbalized before—things you'd normally show someone visually, and say "do it like this".  

For the following prompt, I wasn't even sure I understood what I was writing, but it felt satisfying to, sometimes mash words together creatively  to get the output I had imagined.

{{< figure src="/img/scrabble35.png" caption="Prompt: Eight tasteful blue squares make a hexagon shape (spaced out) in the penultimate concentric square of the grid." >}}

#### Easter Eggs

In one instance of asking Claude to add a tile to the bag containing the letters "A" and "G", Claude chooses to add "M". Asking it to add two more tiles, just because I thought five would look better, Claude adds in "E" and "S" and notes that it spells "G", "A", "M", "E", "S". 

{{< figure src="/img/scrabble18-26.gif" caption="Claude spells 'GAMES' with the letters in the bag." >}}

## Limitations

### Falters with Complexity

Claude 3.5 Sonnet struggles with large, complex asks that require multiple decisions. 

The first prompt I gave it in the Scrabble explainer was to attempt a large chunk of the explainer in one shot.

{{< figure src="/img/scrabble1.png" caption="Generate a simplified diagram for illustrative and instructional purposes representing a Scrabble board in HTML and CSS. Place 7 tiles on the bottom and right of the board." >}}

The diagram left a lot to be desired, and both the grid and premium tiles had errors.

Manipulating the grid and centering multiple elements were major sticking points that 3.5 Sonnet couldn't handle. 

For both the *Scrabble* and the *Codenames* explainers, 3.5 Sonnet is not able to render forked or branching arrows that point from one element to another, which makes sense due to the medium it's working in.

Generally, 3.5 Sonnet performed best when making one-hop iterative changes.

### The Monkey's Paw

The flipside of Claude adhering to precise instructions is that sometimes, Claude will try to precisely adhere to the precise instructions, so they'd better be precisely what you intended. 

If your image is using slightly desaturated colors, but you don't specify the blue you want, well, Claude might use 'blue', #0000FF. If there are two "T"s on the *Scrabble* grid, and only one of makes sense to adjoin letters to, you still had better have specified which "T". And so on. 

### Context Limits

After enough time iterating in one chat instance, the history grows with diminishing returns. Context you may need, like colors or HTML elements are likely present in new iterations, and early versions may not be needed. I found it relatively easy to start a new chat every so often, but this is something to keep in mind.

## Final Thoughts

Artifacts for iterative diagramming makes good use of rendering elements in a display without obstructing the text chat. I expect strengths to improve and limitations to decrease as model capabilities improve. I understand that it's not the UIs sole job to *be* an image editor, but there's a lot of potential in additional tools that could further tighten this workflow.