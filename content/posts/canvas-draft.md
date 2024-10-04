+++
title = '🚧 Canvas as a Collaborative Writing Tool'
date = 2024-10-03T17:00:00-04:00
draft = false
+++

This post is marked with a '🚧', which means it is entirely informal and stream-of-consciousness. It may not make any sense without being linked to with context.

### Canvas

I recently used Claude Artifacts for iterative diagramming. OpenAI came out with Canvas today, an interface built for collaboration within ChatGPT for code and writing. 

I started exploring Canvas for iterative diagramming just to explore, but found some of its most prominent features go unutilized in that use case.

Whereas rapid-fire dictating requests at Claude with Artifacts kind of felt right, especially since code can't be edited directly in the Artifacts pane, it didn't feel that way with Canvas. (Maybe it's a thing of model capabilities or the fact that code couldn't be rendered) So, this post is a pivot from diagramming to writing, to explore a more collaborative use case—editing a blog post in the Canvas pane.

 ### Writing with Canvas

 I give Canvas my draft.
 
 > I have a post: Can you help me clean it up and flesh it out?

I immediately notice some of the language is changed due to my system prompt for ChatGPT which instructs it to use brief, hypercasual language. I'll remove my system prompt and restart.

Running it again, I notice that ChatGPT opted for basically a total rewrite, I'll tell it to maintain the original state of the text so I can edit more precisely. It says it has done so, but it's not my text. After doubling down, it still is unable to provide the original text. Maybe I need to include 'maintain the original text' in the initial prompt. I did ask it to clean it up, so that's on me. Let's restart.

This time, I tell it to just open a canvas:

> I have a post. Open a Canvas: [POST TEXT]

I'm going to hit the "Suggest Edits" button. I go through each edit and apply some of them. I find myself hitting CTRL-Z to roll back an edit, but it doesn't work. I can't really even find where it made the edit after I've applied it since the highlighting disappears. I can restore a previous version though, so I do.

There's a "Final Polish" button, so I'll try that. I think it made some changes, but I can't track the diffs, even if I go to restore a previous version. It's making it hard to understand what was changed.

The output pane says "I've added some final polish, checked grammar, improved readability, and ensured consistency throughout the text. Let me know if there's anything else you'd like me to adjust." which is an undescriptive account of the changes. I like the display of the action it took: currently it says "Edited" above the output, but it would be nice if there were a toggle like in o1 and a more detailed set of actions was displayed.

I'll roll back to a previous version and keep exploring.

I'll ask for some targeted paragraph-level changes and additions now.

I'll ask it to write the Conclusion. It begins streaming output. However, I don't like that I can't tell what was changed before the conclusion. I'll roll it back.

Now, instead of asking for edits through the pane, I'll ask for them by highlighting text and asking for a targeted edit. There is no document-level streaming, which makes me feel better about not having to account for diffs outside of the line I'm aiming to change. The text is changed and looks good. I wonder if it would be too computationally expensive to have an "Accept change" per targeted edit. I think I would like that. It'd essentially be a rollback with a slightly different display.

I'm going to pause this exercise here too, as I think I have enough information now to write a "Takeaways" post.