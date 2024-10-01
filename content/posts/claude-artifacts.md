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

### Create as you Brainstorm

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

Prompting Claude to:
"Render a 👛, relatively medium to large to the right of the game board" or "Increase the black outer stroke on the tiles and game board significantly, and make them dark black" generated outcomes that I was satisfied with in one try, and it was pleasant receiving those although the prompt included fuzzy descriptors like "medium to large" or "significantly".

{{< figure src="/img/scrabble12.png" caption="Render a 👛, relatively medium to large to the right of the game board.">}}


{{< figure src="/img/scrabble13.png" caption="Increase the black outer stroke on the tiles." >}}


#### Spellcasting

This exercise made visceral the importance of word choice while prompting.  

Sometimes you'll want to request something that you may not have really verbalized before—things you'd normally show someone visually, and say "do it like this".  

For the following prompt, I wasn't even sure I understood what I was writing, but it felt satisfying to, sometimes mash words together creatively  to get the output I had imagined.

{{< figure src="/img/scrabble35.png" caption="> Eight tasteful blue squares make an hexagon shape (spaced out) in the penultimate concentric square of the grid.
" >}}

#### Software




## Limitations

### Falters with Complexity

### Requires Clarity

### Context Limits


