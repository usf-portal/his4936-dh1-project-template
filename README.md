# Hacking History
<small>For students of HIS4936 at the University of South Florida</small>

**REQUIREMENTS BEFORE STARTING**
+ [GitHub account](https://github.com) created
+ [GitHub Desktop](https://desktop.github.com) client installed
+ [Atom](https://atom.io) editor installed
+ [Python 3.x](https://www.python.org/) installed

## Project Template

This is a starter template for final projects. When you have completed your final project, you should replace this message (README.md) with a short 1-2 paragraph description of your project.

## Getting a Copy

To begin working on the project, you need 'fork' this repository. This creates a copy tied to your account on GitHub's server. Then you need to 'clone' the remote version of the repository to your local computer to begin working with it. Once you start making changes, you can push them back to your account on GitHub's server.

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_fork.jpg)

---

Assuming you are at the main GitHub page for this repository, click the "Fork" button near the top right of the page (circled in the above picture). This will make an exact copy of the repository, with the same name, but under your account instead. Now that you have a version on GitHub's server (known as the remote copy), you need to clone it to your computer (known as the local copy). Eventually, you will make changes that will be sent back to the remote copy.

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_clone.jpg)

---

Open your GitHub Desktop client, and click the add menu (the '+' button) near the top left of the main window (circled in the above image). That will open a submenu. Next, click the 'clone' tab (also circled), to see a list of all repositories you have access to on the remote server. Click his4936-starter project, and finally choose 'clone this repository.' GitHub Desktop may ask you where you want to put the repository at this point, so decide a convenient location. Congratulations, you can now start making changes.

## Making Changes

You can add/remove files to this repository folder using Explorer (Windows) or Finder (Mac) just like any other. But, for working on the meat of the project, the best way is to work inside of your plain text editor, [Atom](https://atom.io).

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_atom.jpg)

---

Assuming that you have installed Atom, you can open the project directly by clicking the 'repository' menu inside GitHub Desktop, and then choosing 'Open in Atom.' Depending on your system, you may also have an 'Open in Atom' shortcut button visible near the top right.

This project uses the Markdown language to generate the final webpages. Markdown files end in .md, and are edited in Atom, or some other plain-text editor. This is not the place for a full explanation of Markdown, but below are a couple useful links.
* For an overview on Markdown syntax, check out this [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* Try this in-browser [Markdown Editor](http://dillinger.io/), it has a live preview

## Committing and Pushing Changes

Once you have made changes to your local copy (see the 'Markdown Help section below for specifics'), you need to 'commit' all of these changes locally. Each time you commit, you create a milestone, preserving your project in different stages. Later, you can roll back to these stages if you need to.

To commit, open your GitHub Desktop client, and make sure you have the his4936-starter project selected on the left-hand tab. Next, click over to the 'Uncommitted Changes tab' near the top of your window (circled in the below picture). You will then see a list of all documents which are new or changed since the last commit (unless there are no changes). If you click any document, the right-hand pane will show the line-by-line breakdown of all changes in the document since the last commit.

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_commit.jpg)

---

Next, each commit must at least have a brief summary message which helps users keep track of all the different commits. Type in a (very) short message describing your changes. Finally, click the 'Commit to Master' (or whatever branch you are working on). You have now successfully committed your changes *locally*.

Although you have successfully committed to your own machine, you will eventually need to upload these changes to the remote server so that they can be viewed on GitHub. To do this, simply click the 'Sync' button near the top-right of the window. Now if you visit the repository on your GitHub account, you should see the changes. You do not have to push these changes to the remote server each time you commit. You can make as many commits locally as you want before syncing all of them to the remote GitHub server. This way, you can make sure everything is the way you want it on your machine, and only upload to GitHub when you are ready for others to access the files.

## Testing Your Project

You probably want to make sure everything looks as you want before uploading your changes to the server. Fortunately, you can use Python to run everything on your machine.

You need to make sure you have the necessary Python dependencies if you want to test the site on your computer. To install them, open your terminal/command prompt, navigate to the folder with this repository, and type `pip install -r requirements.txt`. If this does not work, try `pip3 install -r requirements.txt`

You will also need to edit the `mkdocs.yml` file in Atom (or other text editor). All of your pages must be located inside the docs directory (or subfolders). You should edit the existing index page (docs/index.md) to your liking, but do not delete or rename it.

To test your project, navigate to your project directory and type `mkdocs serve`. Then, go to your browser and enter `127.0.0.1:8000` into the URL bar. You should see your main index page.

## Working with Branches

When working as a team, changes made by one person might adversely affect the work of another person. That is why it is best to create different branches. To create a new branch, open your project in GitHub Desktop client and click 'Create New Branch' button (circled in the picture below). Type in the desired name of your new branch. Notice that there is a 'from' option. This tells it which branch acts as its 'parent'. Unless you already have made branches, right now you can only choose 'Master.' Then click 'Create Branch'.

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_branch_new.jpg)

---

You now have a new branch on your local machine. But not on the remote GitHub website. To do so, simply click the 'Sync' button again, and it should push your new branch to the remote server.

You can switch back and forth between which branch you are working on by clicking the button immediately to the right of the add new branch button. This will actively swap files in and out, not only in GitHub Desktop and Atom, but also in your Explorer/Finder window. If you can't find files or changes you know you have made, make sure you are on the right branch!

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_branch_remote.jpg)

---

To view the status of different branches on the remote server, head to the GitHub repository webpage. There, just above where the files are listed, you should see a button that says something like 'Branch: Master' (circled in the picture above). Click it to see a list of all the branches that have been created on the remote server. Choose one, and you can then view the files for that branch.

Eventually, you will probably want to merge the changes you make in one branch back to its parent. Say that I made a new branch called 'development'. While I am working on it, I don't want these files to replace the master branch. So, working on the development branch, I made changes to this branch on my local machine. In addition, at various times I synced these changes to the remote version of the development branch. Finally, after making a number of commits and pushes, I am satisfied with everything. Now, I want to merge all of these changes up to the master branch at once.

To do this, I need to create what is known as a 'Pull Request'. Simply click the button marked 'Pull Request' (just above the Sync button), and a new pane will Open. You can then set which branch pulls from which. You should have the branch you want the changes to merge INTO on the left (probably master, if it is your first attempt), and which branch you want the changes to come FROM on the right (in my case, development). Much like making a commit, I can then enter a short summary message and an optional longer description message.

We are almost done, the only remaining step is to approve the pull request on the remote GitHub website itself. Although anyone can generate a pull request, the owner of the repository (or authorized user) must approve it before changes will appear on the remote site. This gives a project manager a last chance to review everything before it becomes finalized.

---

[![Link to Image](docs/imgs/included/screenshot.jpg)](docs/imgs/included/git_pull.jpg)

---

Going to the website, click over to the 'Pull Requests' tab (circled above). If (and only if) a pull requests have been made, they will then be listed below. They should include the summary message, as well as which branches are involved in the request. Click the pull request you want to approve to get the details. If you are satisfied, click the 'merge pull request' request button, and then 'merge branches' (or something to that effect). The changes should now take effect.

**ADD SECTION HERE ON BRINGING CHANGES MADE FROM PARENT BRANCH INTO CHILD BRANCH**

## Team Strategies

* Only update the Master branch with fully polished changes
* Create a development branch from the master, only update it with changes you want the whole team to have access to
* Create sub-branches of the development branch for each team member (or for each section of the site)
* Each team member works on their own branch, only making pull requests to the development branch when they have changes ready that they want other team members to see.
* Once the development branch has been polished, the team leader then creates/approves a pull request to the master branch
