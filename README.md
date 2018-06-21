# Short Introduction to Managing your GitHub Account

1. Go to your GitHub account.

2. Click on the green button _New_ to create a new repository.

3. Fill in the fields _Repository name_ and _Description_, and select the option _Private_ in order to prepare everything before making the repository public.

4. Click on _Create repository_. This will create a new empty and private repository.

5. A _Quick setup_ page will show up with a few instructions to set up your repository.

6. Later, once your repository is ready to be visible, go to the _Settings_ tab in the GitHub repository, to _Options_ and in the _Danger Zone_ you can make the repository public or delete it.


## Linux Users

### Installing and Configuring Git

Git is the software that we use in this guide to track the changes in the files of our local repository. 

From [Wikipedia](https://en.wikipedia.org/wiki/Git):

> Git is a version control system for tracking changes in computer files and coordinating work on those files among multiple people.

First of all, we have to download and install Git in case it is not currently available in our system. In the Ubuntu terminal type

```sh
apt-get install git
```

One installed, a very basic configuration information needs to be provided as well

```sh
git config --global user.name "username"
git config --global user.email emailaddress@example.com
```

The username and email address do not have to coincide with the ones used to create the GitHub account. This configuration data must be provided once and you can overwrite it later by using the previous commands

```sh
git config --global user.name "username2"
git config --global user.email emailaddress2@example.com
```

The configuration data can be checked just by typing

```sh
git config --list
```

Git help can be very useful,

```
git help
git help <command>
git <command> --help
man git-<command>
```

### Working with Git and GitHub

Go to your existing local repository,

```sh
cd myLocalRepository
```

or create a new one,

```sh
mkdir myLocalRepository
cd myLocalRepository
```

Make sure it is not already an initialized repository by typing

```sh
ls -a
```

A list of files and folders contained in _myLocalRepository_ will be printed on screen. If a folder _.git_ already exists, it is advisable to remove it with

```sh
rm -r .git -f
```

Initialize your local repository with

```sh
git init
```

You can generate as well a _.gitignore_ file with folder names and files extensions to be ignored when tracking the contents of your repository. To create such text file type in the terminal

```sh
nano .gitignore
```

and save it with ```CTRL + o```. For instance, adding

```
*.csv
*dynamicCode*
```

will prevent _git_ to keep track of the changes in files and folders with _csv_ extension or containing the string _dynamicCode_.

Now type

```sh
git add -A
git commit -m "first commit"
git remote add origin https://github.com/ChairOfComputationalMathematics/RepositoryName.git
git push -u origin master
```

to add file contents to the index, record the changes to the repository and link the local repository to the GitHub one.

Every time you make changes to your local repository these can be updated in the remote repository by typing

```sh
git commit -a -m "mymessage"
git push
```

Your GitHub user and password will be requested in order to upload the changes. If additional files are created in your local repository, the git index must be updated before committing and pushing the changes,

```sh
git add filename
git commit -m "mymessage"
git push
```

```sh
git add -A
```

adds all the new files to the repository index. The status of the working tree can be checked at any time with

```sh
git status
```

## Generating a README.md File for your Repository

An important step when sharing a repository is generating a README.md file with basic information about the purpose of the code. This file must be written following the Markdown language syntax:
* [Wikipedia-Markdown](https://en.wikipedia.org/wiki/Markdown)
* [Mastering-Markdown](https://guides.github.com/features/mastering-markdown/)
* [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Markdown-Cheatsheet.pdf](https://enterprise.github.com/downloads/en/markdown-cheatsheet.pdf)

Basic Latex equations can be visualized by inserting images generated externally in [codecogs](https://www.codecogs.com/latex/eqneditor.php). Enter your Latex code in the upper box and extract the URL Encoded shown in the lower box.

**Tip.** In order to learn how to use the Markdown language for GitHub it is very instructive to check the README.md files in other repositories. These files are merely plain text that can be open with any text editor. 


## References

* [Git Documentation](https://git-scm.com/doc)
* [Git Guide (Spanish)](https://git-scm.com/book/es/v2)
