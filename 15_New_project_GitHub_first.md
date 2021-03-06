15 New project, GitHub first
================
Boukara Ahmed El-Hachemi
03/07/2020

We create a new Project, with the preferred “GitHub first, then RStudio”
sequence. Why do we prefer this? Because this method of copying the
Project from GitHub to your computer also sets up the local Git
repository for immediate pulling and pushing. Under the hood, we are
doing `git clone`.

## 1 Make a repo on GitHub

<https://github.com> or <https://gitlab.com> or <https://bitbucket.org>.

## 2 New RStudio Project via git clone

In RStudio, start a new Project:

  - *File \> New Project \> Version Control \> Git*. In the “repository
    URL” paste the URL of your new GitHub repository. It will be
    something like this `https://github.com/jennybc/myrepo.git`.  
  - Be intentional about where you create this Project.  
  - Suggest you “Open in new session”.  
  - Click “Create Project” to create a new directory, which will be all
    of these things:
      - a directory or “folder” on your computer  
      - a Git repository, linked to a remote GitHub repository  
      - an RStudio Project  
  - **In the absence of other constraints, I suggest that all of your R
    projects have exactly this set-up**.

There’s a big advantage to the “GitHub first, then RStudio” workflow:
the remote GitHub repo is added as a remote for your local repo and your
local master branch is now tracking master on GitHub. This is a
technical but important point about Git. The practical implication is
that you are now set up to push and pull. No need to fanny around
setting up Git remotes and tracking branches on the command line.

### 2.1 Optional: peek under the hood

Completely optional activity: use command line Git to see what we’re
talking about above, i.e. the remote and tracking branch setup.

`git remote -v` or `git remote --verbose` shows the remotes you have
setup.

``` bash
git remote -v
```

`git branch -vv` prints info about the current branch. In particular, we
can see that local `master` is tracking the `master` branch on `origin`,
a.k.a. `origin/master`.

``` bash
git branch -vv
```

`git clone`, which RStudio did for us, sets all of this up
automatically. This is why “GitHub first, then RStudio” is the preferred
way to start projects early in your Git/GitHub life.

## 3 Make local changes, save, commit

**Do this every time you finish a valuable chunk of work, probably many
times a day.**

From RStudio, modify the `README.md` file, e.g., by adding the line
“This is a line from RStudio”. Save your changes.

## 4 Push your local changes to GitHub

**Do this a few times a day, but possibly less often than you commit.**

You have new work in your local Git repository, but the changes are not
online yet.

This will seem counterintuitive, but first let’s stop and pull from
GitHub.

Why? Establish this habit for the future\! If you make changes to the
repo in the browser or from another machine or (one day) a collaborator
has pushed, you will be happier if you pull those changes in before you
attempt to push.

Click the blue “Pull” button in the “Git” tab in RStudio. I doubt
anything will happen, i.e. you’ll get the message “Already up-to-date.”
This is just to establish a habit.

Click the green “Push” button to send your local changes to GitHub.

# 5\. Confirm the local change propagated to the Github remote

Go back to the browser. I assume we’re still viewing your new GitHub
repo.

Refresh.

You should see the new “This is a line from RStudio” in the README.

If you click on “commits,” you should see one with the message “Commit
from RStudio”.
