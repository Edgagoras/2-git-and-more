# 2.4-Python-basics-notebook

### Python data science tools
For your 
[reading assignments this week](http://www.greenteapress.com/thinkpython2/html/index.html) (Chapters 1-4) you will be starting to learn Python using an online tutorial. This
will introduce the core concepts and data structures in Python.  
Therefore, I won't repeat the introduction to Python here, but rather, 
the goal in this page is to get comfortable with using Python from within an 
environment that allows you to run your code interactively, to save a nice record
of your history, and to share the resulting document with others. 
For this we will be using [Jupyter notebooks](http://jupyter.org/), 
which we introduced and installed using conda during the second lecture. 

To start a jupyter notebook open a terminal and enter `jupyter-notebook`. This will
start a *local server* that will open in a browser at an address called `localhost:8888`. 
From this app you can start notebook documents by clicking on the 'New' tab, and then 'Python'.
Leave the notebook server running in the terminal, if you stop it then the notebooks will 
stop running as well.

```bash
## command to start a notebook on different systems unless otherwise aliased
jupyter-notebook  [Linux, MacOSX]
jupyter.exe       [git-bash]
```

When you start a notebook document it creates a file in your current directory called 
`Untitled.ipynb`. Change the name of this document by clicking on the title 
at the top of the notebook and typing `pytutorial-1-<yourname>`.
Use this notebook as your note pad and testing ground for taking notes 
while learning from the [tutorial reading for this week](http://www.greenteapress.com/thinkpython2/html/index.html), and for running example code from the tutorial. 


### Markdown in the notebook
You should be getting pretty good at Markdown by now. Notebooks are great for 
combining markdown with code since now instead of just pasting code that 
you ran in a terminal into a Markdown document, we can instead execute the code 
directly in the notebook while still writing Markdown in cells around it. 
Select the first cell with your cursor and write the header "# pytutorial-1". 
In the toolbar of the notebook find a dropdown to toggle the cell type from
`code` to `Markdown`. Use this whenever you want to fill a cell with formatted
markdown text vs code. Click on `Help` in the toolbar and select 
`Keyboard Shortcuts` to see a list of shortcuts for all sorts of things,
including switching cell types between `code` and `Markdown`. Learning 
the keyboard shortcuts will make you a faster and more effective user. 


### Code in the notebook
Each cell in the notebook is ready to execute Python code by default. Write
code into the cell like below and press `control+enter` to execute it. 
```python
print("hello world")
```

Also try pressing `shift + enter` on a cell. This executes the cell and 
advances your cursor to the next cell. 


### Stopping a notebook
When you finish taking notes and running code in your notebook you can save it 
with the save button (it auto-saves frequently too). To quit the notebook 
document go to `File` in the toolbar, and then `Close and Halt`, or, 
you can just close the tabs in your browser. If you only close the tabs then 
the notebooks will still be there, since the notebook server is still 
running, and you can reconnect later. But let's stop the notebook server now. 
For this, go to your terminal running the notebook server and press `control + c`
to terminate it. 


### Re-opening notebooks
You can restart your notebook server at any time and it will re-open a view of 
your filesystem. Select the notebook you used last time to continue working on 
it or create a new notebook. 


### Assignment: push your notebook to GitHub
Follow the instructions from the repository `2.3-forking-assignment` 
to fork the repository `https://github.com/programming-for-bio/2-git-and-more.git`, 
and add, commit, and push your notebook (.ipynb file) to the `assignment/` 
directory of your new fork. Remember to put your name in the name of the notebook.
Finally, make a pull request to the `upstream` branch in the programming-for-bio 
Organization. 



