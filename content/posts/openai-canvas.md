+++
title = 'Canvas: First Impressions and Artifacts Comparisons'
date = 2024-10-03T18:46:29-04:00
weight = 1
draft = false
cover.image = "/img/canvasicon.png"
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

I have a detailed, stream-of-consciousness account of my attempt at iterative diagramming with Canvas [here](https://gillandsiphon.github.io/posts/chatgpt-canvas/), but the gist of is that I lobbed it with iterative requests to generate HTML. I used the exercise as a way to understand what iteration and collaboration could look like in Canvas. Although I don't think I cracked the code here, I think I did surface some initial strengths and limitations.

### (Promising) Strengths

#### General Editability

I rarely used editability in my process generating HTML with Canvas, and I now recognize it's not the kind of task that necessitates notebook-like editing. But despite that, editability is a big deal: if I want to change elements in the code I can just do them painlessly inline instead of wasting tokens going through a prompt and regen or manually making edits in an editor while moving outside the UI.

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

### Limitations

#### When do I use this?

I'm not really sure when I should or would use Canvas. If I'm coding, I'm doing it in an IDE. If I run into a problem, I'll tab over to ChatGPT and resolve it. I think Canvas could engulf some of those use cases: adding comments, hitting "Fix Bugs" instead of basically asking for that through a prompt, maybe asking for a code review from time to time. But I'm unsure when I'd actually be editing *in* Canvas. And if I was, I'm unsure what I'd be making, especially without renderability, but even past that, I'd want to run the thing, or debug the thing, or access my data through the thing.

Maybe the audience is different? Maybe it's great for things that don't need to be rendered or ran, like practicing Leetcode questions? I'm not sure.

##### Artifacts

Artifacts basically gets past this with rendering, publishing and remixing, and not offering editability. I think it's a hard problem to figure out how editability works for most people in the web browser.

#### Diffs

I mentioned highlighting in the Code Review section because I really want it in Versioning. Between iterations and when visiting previous instances of my code, I'd really like to know what changed in the panel. Right now, sometimes when I try to roll back from Version now to Version a-long-time-ago, I entirely lose track of where I am and what changed while I backtrack. Numbering the Canvas versions could also help, as could adding a toggle in the text UI to show action text more detailed than "Added 5 comments" or "Edited".


#### Download

As there's no renderability yet (but even if there was), a download button would be useful.

## Writing

The second mode Canvas can detect right now is writing. To explore the writing mode, I attempted to revise a blog post draft and see what kind of workflow arises.

### Strengths

#### The Pane Itself

It's just really nice to see documents in this separate pane. It's one of the nicest things about Artifacts, and I'm glad to have it here too.

#### General Editability

Editability in the writing Canvas pane seems like a big unlock. The UI comes to resemble a word processor. That being said, I struggle to fit it into a workflow for a few reasons I'll detail in the Limitations section.

#### Targeted Editability

Targeted editability is really important too, as I wouldn't want my earlier words to be changed if I'm just looking to improve the syntax on one awkward sentence. More on this in Limitations.

#### Buttons

As in the code pane, the writing pane has the buttons "Add Emojis", "Add Final Polish", "Reading Level", "Adjust the Length", "Suggest Edits". Of these, again, most could have been accomplished by a prompt, although clicking a button is way easier. However, for the same reasons as "Code Review" (highlighting and discretion to apply suggestions), "Suggest Edits" is great. 

### Limitations

#### When do I use this?

I do sometimes bring in writings into ChatGPT or Claude—maybe they're a tricky situation with the landlord or an email where it's tough to land somewhere between casual and formal. In most of those cases, the text is plopped into the chat and commented on, with an entirely new output. I can see all of these cases thrive with LLMs, with or without Canvas. Shorten an iMessage to the property manager, fix up an extension request before you send it to your professor, polish an email to your dermatologist and so on.


But there are other writings that I work on, more longform, more serious, that I don't really edit with models. Canvas editability seems to offer a glimmer of possibility here, but some of the following limitations stopped me from discovering the right use case and workflow.

#### Diffs/Redlines

As with code, I think keeping track of changes is even more important with writing. Code may not run if you change something, but I would feel pretty rough if a sentence in my second paragraph was changed without knowing. I think keeping track of changes made in both versioning and instances where I'm accepting edit suggestions, or adding a conclusion through the text UI would be helpful.

#### System Prompt is Reflected

I passed in a blog draft and asked for it to be cleaned up. My global custom instructions tell ChatGPT to be very casual, and the system opted for a general rewrite that adhered to those custom instructions. I would love for custom instructions to either be ignored for Canvas, or for separate Canvas instructions to be written.

#### Full Rewrite Trigger

The release post mentions the difference between a [general rewrite and a targeted edit trigger](https://openai.com/index/introducing-canvas/), and although I asked for ChatGPT to clean up my draft, which triggered a general rewrite, I wasn't prepared for how it felt when I was not able to induce my original text into the Canvas pane in that chat instance.

#### Word Processor Muscle Memory

I found myself hitting CTRL-Z to roll back edits, but that didn't work. 

#### Action Display

So far, I've seen all action displays above the text prompt say "Edited". It would be nice if this were more detailed. 

#### Asking to Add a Conclusion

I asked for a conclusion to be added to my incomplete draft, but I didn't want my earlier work to be changed, but could not be sure that it would not. I wonder if the text contained in the Canvas is stored and displayed separate from the chat context? I am wondering if there are technical ways to ensure that other areas are not changed by leaving them out of the text generated in a chatcompletion (?) instance.

### Conclusion

It's cool to see the UI evolve, from both OpenAI and Anthropic, and see how different use cases and workflows are discovered. I'm interested to see what kinds of audiences find what kinds of use cases unlocked by these features.