# github-workshop

(Readme in progress)

A workshop teaching the basics of Github with the purpose of empowering others with the necessary skills needed to push code to an open source project.

The following instructions assume you're working on a Mac. More info. on getting setup on other operating systems can be found on Github: https://help.github.com/articles/set-up-git/#platform-mac

Create a Github account:

1. Go to https://github.com/ and sign up.

Getting setup with Git

More information here: https://help.github.com/articles/set-up-git/

Download and install the latest version of Git.

1. Installation varies depending on your operating system. See this page for more details: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

2. There are several ways to install Git on a Mac. The easiest is probably to install the Xcode Command Line Tools. On Mavericks (10.9) or above you can do this simply by trying to run git from the Terminal the very first time. If you don’t have it installed already, it will prompt you to install it.

3. If you want a more up to date version, you can also install it via a binary installer. An OSX Git installer is maintained and available for download at the Git website, at http://git-scm.com/download/mac.

Configure Git

1. On your computer, open the Terminal application.

2. Tell Git your name so your commits will be properly labeled. git config --global user.name "YOUR NAME"

3. Tell Git the email address that will be associated with your Git commits. The email you specify should be the same one found in your email settings. git config --global user.email "YOUR EMAIL ADDRESS"

Authenticate with Github from Git

1. Authenticate with Github from Git. There are two options: connecting over HTTPS, and connecting over SSH. We're going to connect over SSH, so that Git remembers your computer and you don't have to re-enter your credentials each time.

2. Open Terminal, and paste the text below, swapping in your Github email address: ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

3. When prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

4. At the prompt, type a secure passphrase.

5. Ensure ssh-agent is enabled: eval "$(ssh-agent -s)"

6 Add your SSH key to the ssh-agent: ssh-add ~/.ssh/id_rsa If you used an existing SSH key rather than generating a new SSH key, you'll need to replace id_rsa in the command with the name of your existing private key file. 

7. Copy the SSH key to your clipboard: pbcopy < ~/.ssh/id_rsa.pub (If pbcopy isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.)

8. Log in to https://github.com/. In the top right corner of any page, click your profile photo, then click Settings.

9. In the user settings sidebar, click SSH and GPG keys.

10. Click New SSH key. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

11. Paste your key into the "Key" field. Paste your key into the "Key" field. Paste your key into the "Key" field.

Setup a Repository

For More detailed instructions here: https://www.atlassian.com/git/tutorials/setting-up-a-repository/

1. Open terminal and use cd to 'change directory' into the root of your project. Type git init. Git init generates a .git subdirectory in your project's root, containing all the necessary metadata for the repo.

2. Now that you're tracking the directory with Git, you'll want to add something and push it to Github, so you can track and manage your progress. It's customary to create a README.md file to describe your project. In Terminal type touch README.md. 

3. Add your readme file to your git log. Type git add README.md. Alternately, you could type git add -A . (including the period). That command translates to git add everything (-A) in the current directory (the period refers the current folder).

4. Type git status. That command will show you the current status of your git tracking. Since you've added a new file, git should tell you as much.

4. After adding items to your git log, git requires you type a message to explain what you've committed to its memory. To commit the most recent additions, type git commit -m "First commit: Adding readme file."

5. Now type git status. Git should tell you you're up-to-date, and that you have one commit. If you had any new changes (additions, deletions, or modifications), they would display in the terminal above the git status command. 

6. Type git log. You should see your last commit displayed. Over time, as you add more commits, this is a useful command to keep track of your progress.

Fork a Repository

Clone a Repository

Most-Used Commands:

git pull

git push

git add

git commit

git status

git checkout

