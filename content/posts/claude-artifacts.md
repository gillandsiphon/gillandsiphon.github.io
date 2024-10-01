+++
title = 'Claude Artifacts for Iterative Diagramming'
date = 2024-09-28T18:46:29-04:00
draft = false
+++

# Explainer Diagrams

I recently used Claude and Artifacts to help me create explanatory diagrams for the board games [*Codenames*](https://gillandsiphon.github.io/posts/codenames-primer/) and [*Scrabble*](https://gillandsiphon.github.io/posts/scrabble-primer/) as I found the original rules too long for a first introduction.

In doing so, I found iterative diagramming with Claude and Artifacts enjoyable. In this post, I want to organize my takeaways. I've also recorded my workflow in an [appendix post](https://gillandsiphon.github.io/posts/scrabble-case-study/).

!["review3"](/img/review3.png)

# Artifacts
 
Models like Claude act as something between a [rubber duck](https://en.wikipedia.org/wiki/Rubber_duck_debugging) and an immediate feedback loop. I've found they facilitate the brainstorming process if only by forcing the user to articulate their vision. These models comment:(UIs) also surface immediate feedback that makes taking a further step actionable.

Anthropic's [Artifacts](https://www.anthropic.com/news/artifacts) really tightens the immediate feedback loop by rendering the, for example, HTML/CSS in a dedicated window alongside the text chat. You see output *as* you brainstorm, and I found it promising to land on a viable design for an instructional diagram working iteratively with Claude.  


## Strengths


### Immediate Feedback

Working with models like Claude in a text-only UI, like the one that serves ChatGPT and most other large models, is a workflow that's technically just as capable at writing HTML and CSS.

However, Anthropic's [Artifacts](https://support.anthropic.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them) feature, which displays content like renderable code or text documents in a dedicated panel, provides immediate feedback by rendering output without occluding the text chat.

Anthropic's [How we built Artifacts](https://www.youtube.com/watch?v=vUdNaAAc4FY) video outlines the way a feedback loop would work without Artifacts: you'd have to copy-paste the output code into an editor, render it or run it, and then tab back to the chat window to do it again. 

Artifacts tightens that feedback loop and makes iterating enjoyable.

### Create as you Brainstorm

Working iteratively with Claude has a kind of lightness. You can start brainstorming without an immediately clear vision, just thumbing at the clay until viable shapes surface. 

[Working on the Scrabble Explainer],(https://gillandsiphon.github.io/posts/scrabble-case-study/#brainstorming), I knew I wanted diagrams that simplify components of Scrabble. Without much more of a plan, it became more clear to me *what I wanted* by being shown the things I didn't want.

### Branching

Sometimes chasing a hunch doesn't work out. I ran into several instances of ideas that didn't fully pan out. Artifacts, and the rest of the UI make it easy to backtrack and continue despite hiccups. 

#### Retry
A prominent Retry button at the bottom of each output is an easy way to reroll if you want to see another variation, or potentially correct an error.

#### Versions
To visually refer to previous artifacts, a Version history is kept within chat, displayed on the bottom of the Artifacts panel. 

#### Edit
Processed prompts can be edited to continue from a "checkpoint" in the chat instance. I found this the most helpful when I accidentally flubbed the prompt or completely abandoned a rabbithole I was heading down.

#### New Chat
If all else fails, code blocks in the text chat and Artifacts pane can be copied with a copy button, and pasted into a new chat instance.


### Delightful Surprises

- surprising details like randomized letter tiles without asking for it




## Limitations

### Falters with Complexity

### Requires Clarity

### Context Limits


