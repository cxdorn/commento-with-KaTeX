# Commento with KaTeX

A fork of [Commento++](https://github.com/souramoo/commentoplusplus), with added support for comments that contain math written with KaTeX (the KaTeX scripts need to be loaded on the webpage). See there (as well as the original [Commento documentation](https://docs.commento.io/)) for installation instructions.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/cxdorn/commento-with-katex)

### Bugfixes

Besides KaTeX support, a few further bugs have been fixed (at the time of forking).

- Editing a comment, collapsing the comments, and opening it again, wrongly deleted the edits.
- Editing the comment, saving the comment, editing it again, then canceling the second edit, led to the first edit wrongly being reversed.
- Using the editing function wrongly overwrote the `commentsMap` variable, leading e.g. to breaking the sorting function
- Deleting a comment removed all children from the DOM (not from the database though thankfully)
- When re-rendering the comments (as nodes in the DOM), the callback function `onDiscardNode` had a condition that threw an error when stumbling over nodes without innerHTML (this bug appeared in particular when using KaTeX).
