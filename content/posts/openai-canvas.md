+++
title = 'Canvas: First Impressions and Artifacts Comparisons'
date = 2024-09-28T18:46:29-04:00
weight = 1
draft = false
+++

# Canvas 

OpenAI released Canvas in beta this week, which is a new interface that allows collaborative, iterative work with ChatGPT. It's currently geared towards writing and coding—the model will open a dedicated, editable pane with a few options geared towards the kind of work it detects. I casually explored both the writing and coding workflows tonight and have garnered some first impressions and feedback.

# Claude's Artifacts

This release is, for me, serendipitious, as I've recently been exploring Anthropic's Artifacts, which is a pretty similar feature: a dedicated pane opens up when Claude detects something artifact-able, fit for iterative work. However, Artifacts and Canvas have different strengths that make using them feel very different.

# Iterative Diagramming

My choice of exercise to explore Canvas' code editing ability is admittedly kind of unfair. 

{{< figure src="/img/review3.png" caption="Examples of diagrams iteratively created using Claude Artifacts" >}}


I've explored [Claude Artifacts](https://gillandsiphon.github.io/posts/claude-artifacts/) for iteratively creating explanatory diagrams in HTML and CSS. Artifacts has the ability to render code, which makes iterating on diagrams possible in the UI. To approximate this result in Canvas, which currently does not render displays, I copy-pasted the HTML each iteration and manually rendered it. I'll do my best to decouple this manual friction from my overview of Canvas. 

## Code

Asking *ChatGPT 4o with canvas* to generate code generally will trigger an inline code pane that can be expanded into the Canvas panel beside the chat UI. The panel displays line numbers, and contains syntax-highlighted code that is, most importantly editable.

I have a detailed, stream-of-consciousness account of my attempt at iterative diagramming with Canvas [here](https://gillandsiphon.github.io/posts/chatgpt-canvas/), but the gist of is that I lobbed it with iterative requests to generate HTML. I used the exercise as a way to understand what kind of collaboration works for code in Canvas. Although I don't think I cracked the code here, I think I did surface some initial strengths and limitations.

### (Promising) Strengths

#### General Editability

I rarely used editablity in my process generating HTML with Canvas, and I now recnogize it's not the kind of task that necessitates notebook-like editing. But despite that, editability is a big deal: if I want to change elements in the code I can just do them painlessly inline instead of wasting tokens going through a prompt and regen or manually making edits in an editor while moving outside the UI.

##### Targeted Editability

Specific lines of code can be asked about or prompted to be edited by selecting them in the Canvas panel and choosing the "Ask ChatGPT" option. I find it useful for explanations, and it looks promising for targeted edits, although I'm not sure what that workflow looks like or what problems would call for serious code editing in Canvas over an IDE with Copilot or a debugger.

!["scraggle16"](/img/scraggle16.png)

##### Artifacts

Artifacts currently doesn't have editability of any kind, and I did run into the above problems (wasting tokens, manually editing) if I needed to make small edits in code.

#### Branching

Collaboration is by nature iterative, and iteration can take you down rabbit holes, some of which you might want to backtrack from. Canvas offers a 'Previous Version' arrow topping the Canvas panel. Clicking it allows you to toggle through versions and restore a previous one. 

!["scraggle15"](/img/scraggle15.png)


##### Artifacts

 Artifacts has [several options](https://gillandsiphon.github.io/posts/claude-artifacts/#branching) for branching, rerolling, or visiting previous versions.

#### Buttons

The code Canvas pane comes with five buttons, "Add Comments", "Add Logs", "Fix Bugs", "Port to a Language", and "Code Review". Most of these could just be accomplished with prompts before Canvas. However, I find "Fix Bugs" and "Code Review" uniquely helpful. 

##### Fix Bugs

Several times in creating the HTML diagrams, output was truncated or buggy. In all of those cases, hitting "Fix Bugs" fixed the bugs, and it's the kind of thing that would be prompted for so often that a button kind of makes sense to reduce friction. I like this.

##### Code Review

There's two things I like about "Code Review":

1. After the code is generally reviewed for improvements outlined briefly in the text output, the portions that were changed are highlighted. This is really helpful, and in my opinion required in other instances, as I'll outline in the Limitations section.

2. Selectable and Apply-able suggestions. I can see how a quick pass at alternative options or subtle bugs can be surfaced by inducing a code review, and the control is still with the user to decide whether or not to apply the change.

!["scraggle17"](/img/scraggle17.png)

##### Artifacts

As far as I know, Artifacts has no detection of different 'modes' which offer prebuilt features beyond rendering documents as text and code as code.