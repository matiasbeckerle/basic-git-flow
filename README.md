# Basic Git flow

An attempt to describe a basic workflow using Git.

# Disclaimer

There are way too many different Git workflows that covers different team's necessities. These steps are the most basic explanation I can think of for anyone who want to start working with Git. I just want to keep it simple and I will avoid to describe edge scenarios or complex flows.

# Flow

In order to represent each step properly we should consider a team of people: Abigail & John.

## Step 1: picking a task

John picks a task that could be anything that requires a modification in the codebase. You can call it feature, improvement, bugfix and so on.

## Step 2: creating a new branch

John [pulls](https://git-scm.com/docs/git-pull) the latests changes from his team in order to have the project codebase up to date. Then with the shinny updated `develop` branch [creates a new branch](https://git-scm.com/docs/git-checkout) in order to start working on the new task.

`develop` is a wide adopted term that refers the most important branch for developers in their daily work. It usually represents an unstable environment where every developer work is integrated continuosly. Take into account that the concept could be named very differently in other teams.

For the new branch the naming could defer between projects. IMHO it doesn't matter too much as long as the work can be quickly tracked down. I've seen several approaches to this and I will try to sumarize:

- `PROJECT-123-fix-memory-leak`. This is the case where the task is tied to a project management tool.
- `johndoe/fix/20170221/PROJECT-123/fix-memory-leak`. It contains almost everything right? Well... actually user and date is available through Git if you want to ommit them.
- `fix-memory-leak`. When there is no project management tool or is a task hard to clasify.

_Note: I like to use lower case and dashes (instead of spaces) as much as I can (except when tied to a project management tool and I need to refer a ticket ID)._

## Step 3: working (the fun part)

John [commits](https://git-scm.com/docs/git-commit) whatever his is working on.

Every commit is local and maybe John wants to share his latest changes with her teammate Abigail wich is working remotely. What he needs to do is to [push](https://git-scm.com/docs/git-push) his work. This also serves as a backup on the cloud.

## Step 4: creating a pull request

John finishes his work. Ensures everything is working and properly tested. At this moment he needs to [create a pull request](https://blog.alphasmanifesto.com/2016/07/11/how-to-create-a-good-pull-request/) in order to obtain feedback from all the members of the team.

A good idea before creating a pull request is to [rebase](https://git-scm.com/docs/git-rebase) all the changes and then push it to the server. Think about the following: while John was working on that "memory leak fix" some other members were also working and integrating modifications into the main branch `develop`. Rebase is like the operation of saying: "ok Git, forget about everything and apply every single of my commits after the latest changes on `develop` because my codebase is outdated".

After doing a rebase & push to the server John can go to the git server UI and [create a pull request](https://blog.alphasmanifesto.com/2016/07/11/how-to-create-a-good-pull-request/).

## Step 5: code review & refining

While Abigail was working on feature X a new pull request shows up. She might be busy at that time so probably opens the pull request at some point and [starts doing a code review](https://blog.alphasmanifesto.com/2016/11/17/how-to-perform-a-good-code-review/).

Depending on the code reviews John might push more changes or not.

The important thing about this step is that everyone in the team feels right about the upcoming changes to be integrated in the codebase, that everything works as expected.

## Step 6: merge

Once that the pull request is approved, John or the technical lead could [merge](https://git-scm.com/docs/git-merge) into `develop` the new set of changes. Before proceeding with the merge a good advice is to performe another rebase because between the moment that the pull request was created until code is merged could have gone some time and other member probably merged more stuff.

_Note: who is in charge of merging the pull request could vary from team to team. At some teams, developers have full autonomy for merging the code themselves after approval. In others, technical lead or the person responsible for technical stuff is the one who merges the changes._
