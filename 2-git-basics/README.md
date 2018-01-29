# 2.2-git-basics

### Getting *git*
Most likely, `git` is already installed on your computer. To check, open a terminal
(or `git-bash` on PC) and type `git --version`. On MacOSX if you do not
have it it should ask you to install it. A git-bash terminal will have `git`
for sure (it's in the name), and Linux almost certainly will as well. 


### Hands on with *git*
By now you should have read the first two chapters of the 
[git-scm book](https://git-scm.com/book/en/v2), and also finished a simple
interactive tutorial [https://try.github.io/](https://try.github.io/) from 
your first homework. If not, do so now. You should therefore now have some 
grasp of what `git` is meant to do. If this is your first time being exposed 
to it, however, then I would not be surprised if you are still feeling a bit
queazy about it. *What exactly does git do again? And how do I remember all 
of those commands from the tutorial?* Don't worry, that feeling is normal. 
Hardly anyone can remember all of the super advanced things that `git` can 
do, but lucky for us, we can do most of the common tasks of `git` with just a few 
commands -- and when you need the other tricky stuff there is always google. 
Now, it's time to get our hands dirty and create some repositories in our 
brand new GitHub accounts. 


### Configure your git
Before we start using `git` let's first make sure our the program is 
configured. This helps to make sure that we get credit for all the 
work that we do. Substitute your creds in and run the commands below.

```bash
git config --global user.name "Deren Eaton"
git config --global user.email "de2356@columbia.edu"
git config --global color.ui "auto"
```


### What is a git repository?
A `git` repository is simply a directory that holds a hidden subdirectory
called `.git/` which is created by the program `git`. You can see hidden 
items (files with a name starting in `'.'`) by using `ls -a` in a directory. 
The files in `.git/` store information about changes that happen in 
the repository. You should never touch these files yourself, thus the 
reason they are hidden. Instead, the program `git` updates these files
when you execute commands with it. 


### Where are the git repositories?
Usually, there will be multiple copies of a git repository in existence, 
with a key feature being that one of the copies is stored on a server (
or generally *distributed* among multiple places), so that it can be 
accessed online by all of the potential users whenever
they wish to interact with it (e.g., get a copy of it, or send changes to it).
These days, the online copy is typically stored on a site like 
[https://github.com](https://github.com), which we will
be using for this class, but it's worth mentioning that there are 
several other competing sites as well, such as [https://bitbucket.org](https://bitbucket.org). 
In a little bit we will introduce 
the concept of 'branches', which are named versions of our repository. 
The version that is on GitHub is referred to `master`, and its location
it referred to as `origin`. So we might call it `origin/master`. When 
we clone a local copy of this branch to our computer we refer to that 
also as `master`, because it's a clone. 


### Creating a repository  
The interactive tutorial [https://try.github.io/](https://try.github.io/) that 
you tried before had you create a new repository by using the command `git init`. 
That's nice to know about, but most often you will create reposities instead
by visiting GitHub in a web browser. So let's do it that way now. 
Here, GitHub is calling `git init` to create an initial copy of the repository
on their server and then we are going to get a local copy of it by cloning.

So, go to your home page on GitHub ([https://github.com](https://github.com)
if you are signed in). In the upper right corner of the screen you should see a small 
plus sign, click on that and select `New repository`. For "Repository title" enter 
"pdsb-test", select that it is a Public repository, and click the box to initialize
with a README file. That's it, you now have a repository that is hosted in the cloud. 
Next step is to clone a local copy to your computer so you can make changes. 


### Cloning a repository
The standard address for a GitHub repository is 
`https://github.com/{user-name}/{repo-name}.git`. 
It's not too hard to remember, but if you forget you can go to the repository page and
click on the large green button that says "Clone or download" to get the address. Using
this address we can download a local copy of the repository in the following way. Make
sure you are in the location where you want to save the repository before running this. 
In my case, I'm putting it in a directory I created for this class called `/home/deren/PDSB/`. 

```bash
## Change directory into the place you wish to store your new repo
cd /home/deren/PDSB/

## Get the repo. Fill in YOUR username and repo name here
git clone https://github.com/{user-name}/pdsb-test.git

## Change directory into the new repo directory
cd pdsb-test/
```

You can now make edits to the REAMDE file, or add new files. Let's create a new file with some
text in it and add it to the repo. 

```bash
## create a new file and stage it
echo "this is a new file" > newfile.txt
git add newfile.txt
```

The file is now 'staged', however, it is not yet in the repository. You can think of it like 
you are staging a photo -- the snapshot in time of the repository that are aiming to save -- 
but you haven't yet taken the photo. You could edit more files and add them to the repo still. 
Once you feel you are ready to take your snapshot then we proceed to use the command `commit`, 
and add a message to record what took place in our snapshot. 

```bash
git commit -m "added newfile.txt"
```

Now if you run `git status` it will say there is nothing to commit. That is because your stage 
is fully recorded in the snapshot, and hasn't changed since. You can see a history of what is 
in your commits by using `git show` or `git log`. 


### Pushing
The final step among the most basic trio of git commands is `push`. Remember
that you `add`, `commit`, then `push`. This sends the commits that we've made 
to another location. We'll get into more below about where that location is 
and specifying it in detail. But in this case, there's only one other location, 
`origin`, and `git` knows to send it to there. To push your changes call the 
command below and enter your credentials if asked. 

```bash
git push
```

And that's it, you should see that your changes have now taken effect on the GitHub
page. You should see the file newfile.txt. 


### Names
Now it is important that we start to use the proper names when referencing
different repositories and states of the repositories.
There is more or less a standard set of names that are used to reference these, 
and everything will be simpler if you stick to this convention. 

So far, in our example above there were two copies of the repository. 
The main copy -- the *production copy* that we want to always keep working -- 
is referred to as `master`. There was a local copy of it, which we call `master`, 
and there was the copy that is still on GitHub which we call `origin/master`. 
Here, `origin` refers to the location the repo originated from, which is
refered to as a type of `remote` -- a location that is not our computer.
I know, it's a lot of terms... and we're just getting started. 

To recap, in the steps above we cloned the repo `master` from a `remote` 
called `origin`, made changes to it, and then pushed those changes back so 
that `origin/master` was updated to match our local copy of `master`. 

### Remotes
We can see the location of our `remotes` by using a git command:

```bash
## show remotes 
git remote show

## show address of a specific remote
git remote show origin
```


### Branching
In the example we just ran we made edits directly on our local copy of `master`
and then pushed them to update `origin/master`. This works fine, and plenty of people
do all of their work with `git` in this way. There's no shame in it. But... some 
would consider it poor form. You see, by working directly on `master` we failed
to maintain a production quality (working) copy. 
**A better way**, then, is to create a *branch* (another local copy) and do edits
on the branch. In this way we always retain a local working copy that we can use
for testing, and which matches the working remote. It really depends how big the 
edits you plan to do are. If it is a super simple little fix then editing on 
`master` is no big deal. If you are doing a major overhaul of the code and it 
might be a while until you finish and have the code working again, then you 
should definitely be working on a separate branch. 

The simplest way to create a new branch and switch to it is with `checkout`:

```bash
## the -b flag means create a new named branch
git checkout -b feature

## See all branches
git branch

## switch back to master
git checkout master

## switch back to feature
git checkout feature
```

### A better workflow
Let's make changes on our feature branch, test it, and if all is good, then we 
will transfer those changes to `master`. 

```bash
## make edits while on feature branch
echo "more text" >> newfile.txt
echo "a new file" > another.txt
echo "a third file" > third.txt

## add and commit the changes
git add newfile.txt
git add another.txt
git add third.txt
git commit -m "now three files"
```

Now, we are going to merge these commits into our `master` branch. 

```bash
## switch back to master
git checkout master

## merge the branch into master
git merge feature
```

If `master` hasn't changed on `origin` then we can go ahead and `push` our updates
to it. However, if changes have happened on `origin/master` then there is a possibility
that our changes may conflict with those. 

### If commits happened on origin/master while we worked on feature
After we merged our feature branch into `master`, but before we push to `origin`
another step that we could do is to check whether any commits happened on
`origin/master`. This could happen if someone else made commits to it, or if 
we made the changes directly on GitHub. The command `git pull` will pull in 
those changes to our `master` branch. 

```bash
## get changes from origin/master
git pull 
```

Our `master` branch it turns out is ahead of `origin/master`, meaning no
changes happened on that branch while we were working. Now we can go ahead
and push our changes. If there had been changes and they did not conflict then
those changes would simply have been `merged` into our `master` branch. If 
there had been a conflict (more than one person edited the same part of a file)
then the files would have `merged` and we would not
be able to `push` to `origin/master` until we edit the files to resolve the 
conflicts. For that, we could simply use a text editor to find and edit the
conflicts which would now be highlighted by `git` in the file. We had no 
conflicts, so let's go ahead and push. 

```bash
## push master to origin
git push 

## remove the feature branch that is finished
git branch -d feature
```


### Git as a time-machine
One of the critical powers of `git` is its utility for time traveling, basically
allowing you to change the state of your repository back to any previous state
it was in at a time that you made a commit. Remember, commits are like photos
capturing a moment in time. So let's practice some time traveling. 

### Traveling back in time
Let's imagine we start to make some small changes on a branch and then realize
that we made a mistake and want to just revert back to the state the files were
in before we started. There are several ways to do this, so we'll walk through a 
few examples below. 

## undo unstaged changes to a file
We make edits to a file but do not get to the point of staging the changes
with `add`. In this case we can revert the file to it's state in the last 
commit using the command `checkout -- <file-name>`. 

```bash
## make a new branch and switch to it
git checkout -b undotest

## add some text to newfile.txt
echo "some bad edits" >> newfile.txt

## see the status (newfile listed under "Changes not staged for commit")
git status

## you change your mind and revert newfile back to its previous state
git checkout -- newfile.txt
```


### undo staged changes to a file
We make edits to a file and then run `git add` to stage it for the next commit, 
but then we change our mind. Here we need to do just one extra step to rewind the
branch that we are on. 

```bash
## check that we are still on the 'undotest' branch
git branch

## add some text to newfile.txt
echo "some bad edits" >> newfile.txt

## stage the changes to the file for the next commit
git add newfile.txt

## see the status (newfile listed under "Changes to be committed")
git status

## you change your mind and want to un-stage the file
git reset HEAD newfile.txt

## and you also want to undo the changes to the file
git checkout -- newfile.txt
```

If you are in a git-bash terminaln you may need to run 
the `git checkout -- newfile.txt` a second time to
undo all of the changes, since git snuck an extra sneaky edit to your file when you 
ran `add` to change the 'newline' characters from the Windows type to the Unix type
so that it would be compatible with other systems. 


## undo committed changes to a file
```bash
## check that we are still on the 'undotest' branch
git branch

## add some text to newfile.txt
echo "some bad edits" >> newfile.txt

## stage and commit the changes
git add newfile.txt
git commit -m "added some bad edits"

## see the status (no files in 'staged' b/c changes were committed)
git status

## see the last commit
git log -1

## reset back to before the last commit (HEAD~ is shorthand for last commit)
git reset HEAD~

## and if you want, undo the changes to the file
git checkout -- newfile.txt
```


### undo all changes on a branch
Here using branches is convenient. Let's say you made many commits to a branch 
and then decided you don't like any of those ideas and you want to go back to 
your old `master` branch. Well, do just that. And if you want, delete the branch
with the bad commits on it. 

```bash
## create new branch
git checkout -b badstuff

## do some dumb commits on this branch
echo "bad stuff" > newfile.txt
git add newfile.txt
git commit -m "a bad commit"

## changed your mind, go back to master and trash this whole branch
git checkout master
git branch -D badstuff
```


### You made changes on master but want instead to have them on a branch
```bash
## let's make some 'accidental' commits on master
git checkout master
echo "some changes" > newfile.txt
git add newfile.txt
git commit -m "some changes to newfile"

## reset master to match origin/master
git reset --hard origin/master

## changes to newfile are still staged, but no longer committed, 
## simply checking out a new branch will allow you to commit
## the changes there instead of on master.
git checkout -b feature
```


### See the history of commits
The `git log` command has a ton of options for displaying the commits that have occurred
in a repository. You can find a lot of details [in the git-scm chapter](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History). Here are some quick examples
```bash
## see just the last 2 commits
git log -2

## see just the commits from today
git log --since=24.hours

## print on one line with the SHA1
git log --pretty=oneline

## to see a graphical history, especially interesting when there are branch merges.
git log --graph --oneline
```



### Summary

You've now learned to `clone`, `add`, `commit`, `push`, and `merge` as well
to time travel with `git`. It's a great start!

You've finished the tutorial on working with a repo that you have ownership
permissions over. Now the next step is to learn to contribute to a repository
that someone else has ownership over. This will be important because we are 
going to use this framework to collaborate on projects together, and submit
homework assignments and code reviews. Please continue on to the next tutorial.




