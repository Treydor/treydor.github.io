---
layout: post
name: Noah Rogers
title: Keep it clean
date: April 24, 2016
blog: true
---

While working on my last project I continued to learn about how to squash commits and why it is important to keep a clean, feature specific commit history. I learned how to do this through the interactive rebase tool.

### Rewriting history
With the interactive rebase tool we can actually choose how we want to clean up our commits. We also have the ability to simply reword our commit messages.

Let's take a look at my totally arbitrary and made-up commit messages. We can view our last four commits with `git rebase -i HEAD~4`.

<pre>
pick 48b1b5d Adds new blog post
pick 8dfa809 Updates examples
pick 1a43144 Corrects typo
pick 85c749f Corrects another typo

# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
</pre>

This is where all the magic happens. Here we can choose to `pick`, `reword`, `squash` or `fixup` our commits. These options are valuable for a few different reasons. For the sake of this post, we'll focus in on the `squash` and `fixup` options.

### Fixup
Looking at our last four commits we know our oldest commit is by far the most important. With `fixup` we can combine our most recent commit in to a previous commit.

<pre>
p 48b1b5d Adds new blog post
f 8dfa809 Updates examples
f 1a43144 Corrects typo
f 85c749f Corrects another typo
</pre>

Here we are declaring that we want to merge our last three commits in to one of our previous commits. Once we save and push our changes we will only see a single commit in our git history.

### Squash
Squashing does much of the same thing. The biggest difference is that `squash` keeps a history of our commit messages.

<pre>
p 48b1b5d Adds new blog post
s 8dfa809 Updates examples
s 1a43144 Corrects typo
s 85c749f Corrects another typo
</pre>

We'll still have only one commit message in our git history, except now we'll have the ability to expand our commit message to see other commits that have been squashed in to it.

Ultimately, knowing how to use these two options can really clean up our commit history. With rebasing we can follow the rule of commit often, but also reap the benefit of having an easy to read, clean commit history.
