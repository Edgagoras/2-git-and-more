# 2.1-GitHub-Pages  


### Github pages
Of the many cool features that GitHub offers, such as facilitating 
collaboration on open source software, perhaps the most widely useful
is that it offers a ton of free online hosted storage space. This is 
of course used to host code, and among the many types of code that it 
hosts is the code that is used to build websites. In this way, you can 
actually use GitHub to host a website for free, and you can even use
your cool coding skills to update it on the fly from a terminal. Here
we will use GitHub to build a profile website using Markdown.


### How does it work?
Although many websites are 'responsive', meaning that they wait for 
some type of input and then generate tables of output in response, 
other types of websites are what is called 'static', which means 
that they are simply a group of HTML pages that link to each other, 
but do not change as the user interacts with them. This may sound 
limiting, but you can do a lot with static web sites, and they actually
have some cool features due to their static nature such as being faster
and more secure. GitHub pages are static websites that can be generated
from simple Markdown documents and can have added styling on top.


### How GitHub comes in
Static websites can be hosted in almost any public web space, but 
hosting on GitHub is particularly nice because they make it *super*
easy to do, and because you can update the website by pushing changes 
to a git repository. The type of site we are going to make
is called a static [Jekyll](https://jekyllrb.com/) website, which is 
the name of the templating system used to style the pages. Jekyll is 
a really flexible framework for design, but the details of that are a bit
outside the scope of this tutorial. Feel free to read more on Jekyll 
to learn how to make a really advanced static site. 
For now, we'll just slap a nice theme on our page. 


### Examples
To see some examples of static Jekyll sites look at the Eaton lab 
website ([http://eaton-lab.org](http://eaton-lab.org)). I also created an 
example while writing this tutorial for a test account 
here ([https://pdsb-test-student.github.io](https://pdsb-test-student.github.io)), 
based on my dog, LD. 


### How to
You'll be shocked how easy this is. Simply go to your GitHub profile 
and create a new repository named `<your-user-name>.github.io`. That's
it. You just made a static jekyll website. It may take a few minutes to 
load the first time it is created, but once it's ready you'll be able to
view it at `https://<your-user-name>.github.io`. The front page will display the 
contents of the README file by default, so you can start editing the 
README file using Markdown and the content will update on your site. 
Create a profile page for yourself with information like your name, 
what you are studying, and maybe an image. If you don't want to make a 
personal site then feel free to make the page about something else, 
like your dog. You can use the on-line editor on GitHub,
or, clone the repo, make commits in your local text editor (e.g., nano
in a terminal), and push the commits. If you're not comfortable with the 
latter strategy yet, you could skip ahead to [part 2 of this assignment](https://github.com/programming-for-bio/2-git-and-more/2-git-basics/) to review and then 
return here to complete this assignment. 


### Adding jekyll themes
To add jekyll themes on top of your basic README file go to the repository
page for your site `https://github.com/<your-user-name>.github.io`, and click
on 'Settings'. Then scroll down to the section title GitHub Pages and select a
theme from the Theme Chooser. This simply adds a file to your repository called
`_config.yml` that tells GitHub which theme to display.


### Adding more files
You can put other files or directories in this repository as well and they will 
also be accessible from a browser. For example, you can access the README 
file from the test student page by going to 
[https://pdsb-test-student.github.io/README.md](https://pdsb-test-student.github.io/README.md)). 
In the eaton-lab repository I added a directory called `pdsb/` and put the 
files for the first assignment in it. In this way you were able to access
the files for the first assignment like this: 
[http://eaton-lab.org/pdsb/iris-data-dirty.csv](http://eaton-lab.org/pdsb/iris-data-dirty.csv). 
As you can see, it creates an accessible filesystem for storing documents
online, similar to Dropbox. It's worth noting, however, that GitHub does 
limit the size of individual files to something like <100 Mb. 






