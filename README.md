# Github Workshop

A great tutorial on basic Git actions can be found [here](https://try.github.io/levels/1/challenges/1)

*(Readme in progress)*

#### The basics of Github.

The following instructions assume you're working on a Mac. More info. on getting setup on other operating systems can be found on Github: https://help.github.com/articles/set-up-git/#platform-mac

##### Create a Github account:

1. Go to [Github](https://github.com/) and sign up.

##### Getting setup with Git

More information [here](https://help.github.com/articles/set-up-git/)

##### Download and install the latest version of Git.

1. Installation varies depending on your operating system. See [this page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for more details.

2. There are several ways to install Git on a Mac. The easiest is probably to install the Xcode Command Line Tools. On Mavericks (10.9) or above you can do this simply by trying to run git from the Terminal the very first time. If you don’t have it installed already, it will prompt you to install it.

3. If you want a more up to date version, you can also install it via a binary installer. An OSX Git installer is maintained and available for download at the [Git website](http://git-scm.com/download/mac).

##### Configure Git

1. On your computer, open the Terminal application.

2. Tell Git your name so your commits will be properly labeled. `git config --global user.name "YOUR NAME"`

3. Tell Git the email address that will be associated with your Git commits. The email you specify should be the same one found in your email settings. `git config --global user.email "YOUR EMAIL ADDRESS"`

##### Authenticate with Github from Git

1. Authenticate with Github from Git. There are two options: connecting over HTTPS, and connecting over SSH. We're going to connect over SSH, so that Git remembers your computer and you don't have to re-enter your credentials each time.

2. Open Terminal, and paste the text below, swapping in your Github email address: `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

3. When prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

4. At the prompt, type a secure passphrase.

5. Ensure ssh-agent is enabled: `eval "$(ssh-agent -s)"`

6 Add your SSH key to the ssh-agent: `ssh-add ~/.ssh/id_rsa` If you used an existing SSH key rather than generating a new SSH key, you'll need to replace id_rsa in the command with the name of your existing private key file. 

7. Copy the SSH key to your clipboard: pbcopy < ~/.ssh/id_rsa.pub (If pbcopy isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.)

8. Log in to [Github](https://github.com/) In the top right corner of any page, click your profile photo, then click Settings.

9. In the user settings sidebar, click SSH and GPG keys.

10. Click New SSH key. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

11. Paste your key into the "Key" field. Paste your key into the "Key" field. Paste your key into the "Key" field.

##### Setup a Repository

For More detailed instructions [here](https://www.atlassian.com/git/tutorials/setting-up-a-repository/)

1. Open terminal and use cd to 'change directory' into the root of your project. Type `git init`. Git init generates a .git subdirectory in your project's root, containing all the necessary metadata for the repo.

2. Now that you're tracking the directory with Git, you'll want to add something and push it to Github, so you can track and manage your progress. It's customary to create a README.md file to describe your project. In Terminal type `touch README.md` 

3. Add your readme file to your git log. Type `git add README.md`. Alternately, you could type `git add -A .` (including the period). That command translates to git add everything (-A) in the current directory (the period refers the current folder).

4. Type `git status` That command will show you the current status of your git tracking. Since you've added a new file, git should tell you as much.

4. After adding items to your git log, git requires you type a message to explain what you've committed to its memory. To commit the most recent additions, type `git commit -m "First commit: Adding readme file."`

5. Now type `git status` Git should tell you you're up-to-date, and that you have one commit. If you had any new changes (additions, deletions, or modifications), they would display in the terminal above the git status command. 

6. Type `git log` You should see your last commit displayed. Over time, as you add more commits, this is a useful command to keep track of your progress.

##### Clone a Repository

1. Let's say you want to contribute to any of the thousands of incredible open-sourced projects on Github. Once you've found a repository you're interested in, you can pull the project code 'local,' meaning onto your computer, so you can add your two cents.

2. Open Terminal. Use the `cd` command to change directory to a folder where you would like the project code to download into. 

3. On the Github repository page, you should see the option to clone using SSH or HTTPS. Choose SSH, and copy the link to your clipboard (either by using the button provided, or by simply highlighting and copying).

4. Back in Terminal, type the following, replacing *repo url* with the SSH url you copied from Github. `git clone *repo-url*`. The project's code will download into a sub-directory.

5. Type the command ls into Terminal. You should see the sub-directory the project's code was downloaded into. In the future, if you'd rather create and name a new directory for the project's code to download into, you can follow the regular git clone command with a directory name of your choosing: `git clone *repo-url* your-new-directory`.

6. Any changes you make to the code in the project you just downloaded will be added to a git log that can be pushed remotely, back up to the repository you cloned from. If you push your code up to the branch you pulled from, the repository's owner will recieve what's called a pull request, which describes the changes you've made, and why they might want to integrate your work with their own. If the repository owner accepts your pull request, you'll now be considered a contributor to whatever project you've been working on!

##### Create a New Branch

1. If you're working on a newly-intialized git directory, by default you'll be on a branch called master. 

2. Usually, you'll create a new branch if you're hoping to create a new feature or work out a bug in your code.

3. Open Terminal and use the cd command to change directory into your project's repository.

4. Type `git checkout -b *your-new-branch-name*` That means you're checking out a new branch with the name you provide. 

5. Once you've created and checked out your new branch, you can always switch back to your master branch, or any others you may have created.

6. Keep in mind that your new branch will pickup whatever changes are in your directory at the creation of your branch. It will also pick up from wherever you were in git tracking on the original branch.

##### Fork a Repository

##### Most-Used Commands:

* `git fetch`: Update your local Git's tracking of what's in the remote repositories.

* `git pull origin *branch-name*`: Pull the most recent code from a specified branch.

* `git push origin *branch-name*`: Push code from a local (your computer) branch to a remote (Github) branch.

* `git add *file-name*`: Add a file to Git's records.

* `git add -A .`: Add everything in the current directory to Git. Be careful, because this can often inadvertently add files you hadn't intended to commit. Not the end of the world if you do (you can always use git checkout *filename* to remove them from Git's memory), but it's sometimes safer to simply add individual files.

* `git commit -m "Your commit message here"`: Commit added changes to Git's tracking system. Git requires a message to describe the changes, so you can better understand changes you've made in retrospect.

* `git status`: Reads out Git's current understanding of your project's progress. This command will show any modifications, additions, or deletions you've made to your project files. It should also

* `git checkout -- *filename*`: Removes a specified file from Git's tracking. 

