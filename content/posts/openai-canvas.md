+++
title = 'Canvas: First Impressions and Artifacts'
date = 2024-09-28T18:46:29-04:00
weight = 1
draft = false
+++

## Canvas 

OpenAI released Canvas in beta this week, which is a new interface that allows collaborative, iterative work with ChatGPT. It's currently geared towards writing and coding—the model will open a dedicated, editable pane with a few options geared towards the kind of work it detects. I casually explored both the writing and coding workflows tonight and have garnered some first impressions and feedback.

### Claude's Artifacts

This release is, for me, serendipitious, as I've recently been exploring Anthropic's Artifacts, which is a pretty similar feature: a dedicated pane opens up when Claude detects something artifact-able, fit for iterative work. However, Artifacts and Canvas have different strengths that make using them feel very different.

## Iterative Diagramming

My choice of exercise to explore Canvas' code editing ability is admittedly kind of unfair. 

{{< figure src="/img/review3.png" caption="Examples of diagrams iteratively created using Claude Artifacts" >}}


I've explored [Claude Artifacts](https://gillandsiphon.github.io/posts/claude-artifacts/) for iteratively creating explanatory diagrams in HTML and CSS. Artifacts has the ability to render code, which makes iterating on diagrams possible in the UI. To approximate this result in Canvas, which currently does not render displays, I copy-pasted the HTML each iteration and manually rendered it. I'll do my best to decouple this manual friction from my overview of Canvas. 

### Code

Asking *ChatGPT 4o with canvas* to generate code generally will trigger an inline code pane that can be expanded into the Canvas panel beside the chat UI. The panel displays line numbers, and contains syntax-highlighted code that is, most importantly editable.

I have a detailed, stream-of-consciousness account of my attempt at iterative diagramming with Canvas [here](https://gillandsiphon.github.io/posts/chatgpt-canvas/), but the gist of is that I lobbed it with iterative requests to generate HTML. I used the exercise as a way to understand what kind of collaboration works for code in Canvas. Although I don't think I cracked the code here, I think I did surface some initial strengths and limitations.

#### Strengths

##### Editability

I rarely used editablity in my process generating HTML with Canvas. However, I concede it's not the kind of task that really calls for it.

Even despite that, the fact that the code was editable is a pretty big deal, and here's an example:

In generating HTML with Claude, which doesn't have an editable Artifacts panel, if I generate 100 lines of HTML and then just want to change a few colors, I'll have to manually change the HTML in a code editor after downloading it, or waste tokens by prompting again. I did find editing useful for changes like this.

But, more that that, I can see how useful editing might be for tasks that actually necessitate fiddling with code, like let's say doing a leetcode problem in Canvas (I'll put it on the list of articles ideas).

#### Versioning

Collaboration is by nature iterative, and iteration can take you down rabbit holes, some of which you might want to backtrack from. Artifacts and Canvas both have mechanisms to roll back iterative changes (You can read about Claude's [here](https://gillandsiphon.github.io/posts/claude-artifacts/#branching)).

##### Previous Version

Canvas offers a 'Previous Version' arrow topping the Canvas panel. Clicking it allows you to toggle through versions and restore a previous one. 

!["scraggle15"](/img/scraggle15.png)

