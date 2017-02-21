# Basic Git flow

An attempt to describe a basic workflow using Git.

## Before start

In order to represent each step properly we should consider a team of people: Abigail & John.

## Flow

### Step 1: picking a task

John picks a task that could be anything that requires a modification in the codebase. Feature, improvement, bugfix.

### Step 2: creating a new branch

John [pulls](https://git-scm.com/docs/git-pull) the latests changes from his team. Then with the shinny updated `develop` branch [creates a new branch](https://git-scm.com/docs/git-checkout) in order to start working on the new task.

`develop` is a wide adopted term that refers the most important branch for developers in their daily work. It usually represents an unstable environment where every developer work is integrated continuosly. Take into account that the concept could be named very differently in other teams.

For the new branch the naming could defer between projects. IMHO it doesn't matter too much as long as the work can be quickly tracked down. I've seen several approaches to this and I will try to sumarize:

- `PROJECT-123-fix-memory-leak`. This is the case where the task is tied to a project management tool.
- `johndoe/fix/20170221/PROJECT-123/fix-memory-leak`. It contains almost everything right? Well... actually user and date is available through Git if you want to ommit them.
- `fix-memory-leak`. When there is no project management tool or is a task hard to clasify.

_Personal note: I like to use lower case and dashes (instead of spaces) as much as I can (except when tied to a project management tool and I need to refer a ticket ID)._

### Step 3: working (the fun part)

John [commits](https://git-scm.com/docs/git-commit) whatever his is working on.

Maybe John wants to share his latest changes with her teammate Abigail wich is working remotely. What he needs to do is to [push](https://git-scm.com/docs/git-push) his work. This also serves as backup on the cloud.
