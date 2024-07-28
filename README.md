# git-documentation-tutorial
A tutorial repository to guide you through how to use git and LaTeX for writing collaborative documentation

# What is Git? What is GitHub?

_**Git**_ is a version control tool that we will be using to manage our documentation. It allows us to track documents at different points in their lifespan and do a whole host of other things which make organising and tracking much easier.

_**GitHub**_ is a website which allows us to use git to collaborate on documents together. We will be hosting all our documentation on GitHub.

# Fundamentals of Git/GitHub

A ***repository*** is essentially a place where the files for a particular project are stored. Our repositories are hosted on GitHub (a bit like google docs) - for this project, the link is https://github.com/tranjamin/git-documentation-tutorial. When online version of the repository is referred to as the _remote_ or the _origin_. You can also **clone** the remote repository onto your laptop, which amounts to downloading it as a local copy. The catch is you can then upload any changes back to the remote repository - this is called a **push**.

Git organises edits into **commits** and **branches**. A commit is simply a collection of changes that you have saved to a particular branch. Git keeps track of every commit you make, letting you go back to earlier commits ("versions") if you want.

When you make edits to a file, you do so on a particular branch. Branches are different copies of the same files which can be worked on in parallel. For example, you usually have a branch for each new feature you want to create so you can make edits without affecting the "official" copy. This is handy because multiple people can work on multiple things at once, and as long as they are on different branches they won't conflict with each other.

Ultimately however, we usually want to combine all of these features into one. We do this on the **main** or **master** branch - this is the "official" branch for the project, and instead of editing it directly we make changes on branches and ***merge*** them in to the main branch. More on how to do this later.

# Downloading

For people who are new to using git/GitHub, we strongly recommend GitHub Desktop, which provides a nice user interface for intereacting with repositories. It is available on both Windows and MacOS (if you're using Linux you probably already know git) and we'll be using it for this tutorial. But you're welcome to use any workflow which works for you.

Download GitHub Desktop: https://desktop.github.com/download/

Download Git: https://git-scm.com/downloads

Run the installers and follow the instructions to sign in to GitHub and configure git.

# Cloning the Repository

On the top left of GitHub Desktop, click File -> Clone repository -> URL and paste in the url of this repository. Click clone to create a local version of the repository.

Click `Fetch origin`. This will sync the latest updates of the remote repository.

# Making Contributions

## Make a new branch

You don't want to directly edit the main branch (in fact, you probably don't have the permissions to). Instead, click on the `Current branch` dropdown and you will be able to make a new branch. Name it something descriptive, like what feature you plan to add using the branch - in this case, you can just name it something like `\<yourname\>-branch`. This will create a new branch based off the branch you were originally on. In this case, it will make a copy of the `main` branch, but any edits you make in your new branch will not be reflected in the main branch.

Once you have created a new branch, you will get a new option: `Publish branch`. This option lets you upload your branch to the remote repository (currently it is only on your local device). You can go ahead and publish your branch.

## Making edits

Click on the `Current branch` dropdown and select which branch you want to edit - in this case, it will be the one you just made. Then go ahead and make a change by adding your name and a blurb to the main.tex file (there's a format in the file you can copy). If you're familiar with LaTex, go ahead and use your preferred workflow (you can click `Show in Explorer` to see where your files are). If you aren't, follow these instructions:

### Editing LaTex Files

Install LaTeX: https://miktex.org/download

Open TeXworks and open the main.tex file (click on `Show in Explorer` in GitHub Desktop to find them).

Click on the green play button at the top left, which will generate the pdf file (you may get asked for permission to install packages - this is okay). Any edit you make won't be reflected to the PDF until you click the generate button. 

## Committing changes

Once you have made a change, you will want to commit ("save") them to your branch. Go back to GitHub Desktop and you will be able to see what changes you've made. Note that only the source files (main.tex) will be there - any other auxiliary files or pdf are intentionally left untracked by git. Towards the bottom left, name your commit, optionally add a description and then click commit (make sure you are committing to the right branch!). Click `Push origin` to upload your changes to the remote repository.

You may have noticed that the GitHub repository does not contain any generated pdf files. This is intentional because we only want to keep track of files we directly make edits to. Instead, this repository has been set up to automatically generate a pdf for every commit that is made. On the GitHub page, under `Actions` you will be able to view all pdfs generated. Filter by the name of the branch and select the most recent workflow. Under artifacts you can then download the corresponding pdf.

# Pull Requests

## Creating a Pull Request

Now you have made changes in a local branch and are happy that everything works, you can merge it into the main branch. Go back to GitHub (https://github.com/tranjamin/git-documentation-tutorial) and click on `Pull requests`. A pull request is an official request you make to have your branch integrated into the main branch.

Click `New pull request` and change the `compare branch"`to your branch. For this one, leave the `base` as `main`. This means that we are going to integrate the changes we made in your branch to the `main` branch. Then click `Create pull request`. Write a title and description of what your branch includes and then click `Create pull request` again. You then need to wait for someone else to review it before it can be approved.

## Reviewing a Pull Request

In order for a branch to be integrated, it needs to be reviewed and approved. This is to maintain the quality of the codebase. In terms of documentation, it suffices to look at the PDF (not the .tex files) and make sure any changes are correct on that. 

Go to `Files Changed` under the pull request page and examine what changes have been made. You should also see the generated PDF file to make sure there are no errors (click `Checks` and then `LaTeX Build PDF` and then download the `main.pdf`). To approve a pull request, click `Review changes` on the right hand side. You can then leave comments and either approve the pull request, make simple comments, or request specific changes to be made. Only an approved pull request can be merged.

## Merging a Pull Request

Once a pull request has been approved, as the creator of the request it is your responsibility to merge it. To do so, click the dropdown next to the `Merge pull request` button and select `Squash and merge`. Usually this is the better option because you don't want to clutter the version history with small commits.You can now make the merge request, and then delete your old branch.

# Next Steps

Congratulations! You have made your first contribution to our GitHub. We've only covered the basics of git, but luckily GitHub Desktop does a lot of the work for us. If you're interested in learning more about git, Atlassian has a very comprehensive guide here: https://www.atlassian.com/git. You can also find more information about using GitHub here: https://docs.github.com/en/get-started/using-github.
