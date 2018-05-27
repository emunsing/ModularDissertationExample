# Creating a Modular Dissertation with Overleaf and Git

This accompanies the full description in [this blog post](http://ecomunsing.com/writing-your-dissertation-or-book-with-overleaf-git). 

The goal is to easily reuse content from journal or conference articles to create the chapters of your dissertation. This is accomplished by creating a dissertation project, then adding the chapters as fake git submodules, using [the workflow described here](http://web-dev.wirt.us/info/git/fake-git-submodules-better-git-inside-git).

## TL;DR:
- Submodules don't work in Git. Add fake repositories instead.
- This means that the changes to the overall project will cascade to the submodules- watch out!
- Sync the individual chapters with Overleaf before syncing the dissertation

Workflow:
- Pull changes from chapter from Overleaf
- Edit each chapter independently
- Push updates to Overleaf
- Push overall dissertation to Overleaf


# Troubleshooting


## File Type conflicts

Overleaf prevents you from pushing .log, .blg, .gz, .aux files. These need to be included in .gitignore.

If you've already committed with these files and are getting an error when you try to push, you can make git forget these files by doing `git rm --cached <file>` and then committing.