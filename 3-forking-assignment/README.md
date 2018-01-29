# 2.3-forking


### fork and submit homework
This will be our first attempt at contributing to a repository that we don't own. 
The general framework is still really similar, basically we are making a 
work-around to accomodate the fact that we need the owner's permission before
the changes that we made take effect on the other person's repo. 

### Names again
This time we will need to worry about at least 3 existing versions of the repository. 
Let's think about locations first. The *other* user's repository is referred
to as `upstream`, while the forked copy that we will have on GitHub 
is refered to as `origin`. Just like before, we will clone from our own 
copy and name this `origin`. Most of our interaction with the `upstream` branch
will take place on GitHub instead of through `git` at the command line. 


### Instructions for submitting your homework
By the end of this assignment everyone in the class will have a forked copy 
of the repository `1-Shell-Basics`. Start by visiting the repo on GitHub at
[https://github.com/programming-for-bio/1-Shell-Basics](https://github.com/programming-for-bio/1-Shell-Basics) and click on "Fork" in the upper right 
corner of the browser page. This should show you that it is forking the repo
and then bring you to your own new fork -- a repo in your GitHub profile that
is under your ownership. You can make changes to this forked repo all that you
want without asking anyone's permission. So we will use the fork as a testing
grounds to push our edited code. When we're happy with the result we will 
finally submit a "pull request" to the `upsteam` repo asking them to accept 
our commits.


Fork the `upstream` repo to get a forked branch in `origin/master`. 
```bash
## fork the upstream repo on GitHub
<click fork button at https://github.com/programming-for-bio/1-Shell-Basics>
```

Clone `origin/master` to get a local copy `master`. 
```bash
## clone your branch and cd into it
git clone https://github.com/<you>/1-Shell-Basics.git
cd 1-Shell-Basics/
```

Copy your markdown assignment from last week to this repo and rename it as your-name.md. 
Add the file to this branch, commit the changes and push to origin. 
```bash
## copy and RENAME your markdown assignment  
cp <path-to-assignment> ./<myname>.txt

## add your markdown assignment file
git add ./<myname>.txt

## commit it
git commit -m "added assignment-1 file"

## push to origin
git push 
```

Now, make a pull request to merge your `origin/master` branch to `upstream`. 
For this, go to your `origin` repo and click the 'New pull request' button. You will
now need to wait until the owner of the upstream repo accepts your pull request for 
the commits to take effect. 

Later, after I have had chance to accept the pull requests from everyone in class
you will be able to see everyone's first assignment answers in the upstream repo, 
and, you can even pull them into your local copy by merging. 
To get updates from the `upstream` repository we need to add it as a remote to 
our git repo. Then we call `fetch` and `merge`, or the equivalent call `pull`
will perform the same task. 

```bash
## add upstream remote
git remote add upstream https://github.com/programming-for-bio/1-Shell-Basics.git

## pull commits (fetch & merge)
git fetch upstream
git merge master

## see all the new files 
ls assignment/
```

