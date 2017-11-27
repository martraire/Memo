#  Git and GitHub

Here are some information about Git and GitHub: How to install Git? How to create and keep traces of the updates of your project? 
Finally, a list of the useful commands in Git and GitHub.


## How to get Git ?
The last version of Git can be downloaded at: http://git-scm.com/downloads.
It is available for all operating systems.

## Define your profile
In order to keep trace of the author and later if using GitHub, it is recommanded to setup an account via these two commands:

```
git config --global user.name "Enter your Name  and Surname"
git config --global user.email "Enter your mail address"
```

## Initialize a project
You are starting a new project and so want to use git:
```
mkdir project
cd project
git init     # initialize the directory as a Git dir.
git status   # check the status of the directory
```


## Basic commands of Git
Here are the main commands used in Git:
- `git add filename`: add the file to Git
- `git commit -m "Comment about the modification in the file or action"`: commit with comment to track modif
- `git log`: list of commit with date, author, legend, ...
- `git -am "Comment of the commit"`: -a for Add and -m basic commit


## Change version: previous or last one
Sometimes, you need to come back to a previous version before a bugg happens or something else. For this, there is a very useful command `git checkout`.
In order to choose the version you want, you need the #SHA of the version (serial number of the version given with `got log`).

1. Go to a previous version: `git checkout #SHA`
2. Go back to the last version: `git checkout master` (By default, the master branch is the last one)


## Copy a GitHub directory on your local machine
**On the GitHub website:**

You have to look at the directory needed and click on **Clone or download**. You have the choice between HTTS or SSH, in this example, let's use HTTPS.
Once you have copied the link, go to your local machine.

**Local machine:**
`git clone #URL`

This command copy the directory from GitHub to your local machine

