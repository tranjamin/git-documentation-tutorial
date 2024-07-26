# git-documentation-tutorial
A tutorial repository to guide you through how to use git and LaTex for writing collaborative documentation

# What is Git? What is GitHub?

Git is version control tool that we will be using to manage our documentation. It allows you to track documents at different points in their lifespan and do a whole host of other things which make organising and tracking much easier.

GitHub is a website which allows us to use git to collaborate on documents together. We will be hosting all our documentation on GitHub.

# Fundamentals of Git/GitHub

A ***repository*** is essentially a project, or a place where a group of files are stored. Our repositories are **hosted** on GitHub - for this project, the link is https://github.com/tranjamin/git-documentation-tutorial. When hosted online, we call this a **remote repository**. You can also **clone** the remote repository onto your laptop, which amounts to downloading it as a local copy. The catch is you can then upload any changes back to the remote repository - this is called a **push**.

Git organises edits on files into **commits** and **branches**. A commit is simply a collection of changes that you have saved to a particular branch. A commit amounts to history - git keeps track of the commits you make and you have the ability to go back to earlier commits ("versions") if you want.

When you make edits to a file, you do so on a particular branch. Branches are ways of bundling a group of commits together. For example, you usually have a branch for each new feature you want to create. This is handy because multiple people can work on multiple things at once, and as long as they are on different branches they won't conflict with each other.

Ultimately however, we usually want to combine all of these features into one. We do this on the **main** or **master** branch - this is the "correct"/"complete"/"professional" branch for the project, and instead of editing it directly we make changes on branches and ***merge*** them in to the main branch. 

# Downloading

For people who are new to using git/GitHub, we strongly recommend GitHub Desktop, which provides a nice user interface for intereacting with repositories. It is available on both Windows and MacOS (if you're using Linux you probably already know git) and we'll be using it for this tutorial. But you're welcome to use any workflow which works for you.

Download GitHub Desktop: https://desktop.github.com/download/

Download Git: https://git-scm.com/downloads

Run the installers and follow the instructions to sign in to GitHub and configure git


# Cloning the Repository

On the top left of GitHub Desktop, click File -> Clone repository -> URL and paste in the url of this repository. Click clone to create a local version of the repository.

Click "Fetch Origin". This will sync the latest updates of the remote repository.

# Making Contributions

## Make a new branch

You don't want to directly edit the main branch (in fact, you probably don't have the permissions to). Instead, click on the "Current branch" dropdown and you will be able to make a new branch. Name it something descriptive, like what feature you plan to add using the branch - in this case, you can just name it something like "\<yourname\>-branch". This will create a new branch based off the branch you were originally on. In this case, it will make a copy of the "main" branch, but any edits you make in your new branch will not be reflected in the main branch.

Once you have created a new branch, you will get a new option: "Publish branch". This option lets you upload your branch to the remote repository (currently it is only on your local device). You can go ahead and publish your branch.

## Making edits

Click on the "Current branch" dropdown and select which branch you want to edit - in this case, it will be the one you just made. Then go ahead and make a change by adding your name to the main.tex file. If you're familiar with LaTex, go ahead and use your preferred workflow (you can click "Show in Explorer" to see where your files are). If you aren't, follow these instructions:

### Editing LaTex Files

Install LaTeX: https://miktex.org/download

Open TeXworks and open the main.tex file (click on "Show in Explorer" in GitHub Desktop to find them).

Click on the green play button at the top left, which will generate the pdf file. Any edit you make won't be reflected to the PDF until you regenerate the pdf.

## Committing changes

Once you have made a change, you will want to commit ("save") them to your branch. Go back to GitHub Desktop and you will be able to see what changes you've made. Note that only the source files (main.tex) will be there - any other auxiliary files or pdf are intentionally left untracked by git. Towards the bottom left, name your commit, optionally add a description and then click commit (make sure you are committing to the right branch!). Click "Push origin" to upload your changes to the remote repository.

# Pull Requests

## Creating a Pull Request

Now you have made changes in a local branch and are happy that everything works, you can merge it into the main branch. Go back to GitHub (https://github.com/tranjamin/git-documentation-tutorial) and click on Pull requests. A pull request is an official request you make to have your branch integrated into the main branch.

Click "New pull request" and change the "compare branch" to your branch. For this one, leave the "base" as main. Then click "Create pull request". Write a title and description of what your branch includes and then click "Create pull request". You then need to wait for someone else to review it before it can be approved.

## Reviewing a Pull Request

In order for a branch to be integrated, it needs to be reviewed and approved. This is to maintain the quality of the codebase. In terms of documentation, it suffices to look at the PDF (not the .tex files) and make sure any changes are correct on that. 

Whenever a commit is made, a PDF file is automatically generated. You can see these files under "Actions". To see the PDF for a pull request, click on "Checks" at the top of the pull request page, then "LaTeX Build PDF" and "main.pdf" under Arfifacts. Have a look at the PDF to make sure any changes made are correct. It is also good to go to "Files Changed" under the pull request page to see exactly where modifications have been made.

To approve a pull request, go to "Files Changed" and "Review changes" on the right hand side. You can then leave comments and either approve the pull request, make simple comments, or request specific changes to be made. Only an approved pull request can be merged

## Merging a Pull Request

Once a pull request has been made, as the creator of the request it is your responsibility to merge it. To do so, click the dropdown next to the "Merge pull request" button and select "Squash and merge". This is recommended because smaller commits are squashed and it makes the file history easier to read. You can now make the merge request, and then delete your old branch.