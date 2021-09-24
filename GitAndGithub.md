# Week 2: Git, Github and Hosting

## Git vs. Github

- **git and GitHub are not the same thing.**
  - Git is an open-source, version control tool created in 2005 by developers working on the Linux operating system.
  - GitHub is a company founded in 2008 that makes tools which integrate with git.
- **You do not need GitHub to use git, but you cannot use GitHub without using git.**
- There are many other alternatives to GitHub, such as GitLab, BitBucket, and “host-your-own” solutions such as gogs and gittea. All of these are referred to in git-speak as “remotes”, and all are completely optional. You do not need to use a remote to use git, but it will make sharing your code with others easier.

## Intro to Git presentation (10 mins)

## Intro to the Linux Shell, aka the "Terminal" (10 mins)

Since the virtual machines being used throughout this bootcamp are configured to use the Linux operating system (OS), it will be useful to have a few of the basic commands under your belt. In short, a shell is a program that receives commands from the user and gives it to the OS to process, and it shows the output. Linux has a Command Line Interface (CLI) that can be interacted with using the following commands (this is a non-exhaustive list, but will be enough to get you started):

- `pwd`: present working directory, gives the absolute path, which means the path that starts from the root. The root is the base of the Linux file system. It is denoted by a forward slash( / ).
- `ls`: lets you know what files are in the directory you are in. You can see all the hidden files by using the command `ls -a`.
- `cd`: lets you change directory e.g. `cd Downloads` will move you to the Downloads directory given you are already in the parent directory. If you just type `cd` and press enter, it takes you to the home directory. To go back from a folder to the folder before that, you can type “cd ..” . The two dots represent back.
- `mkdir`: lets you create a new folder or directory e.g. `mkdir new_folder_name_here`.
- `rmdir`: lets you delete a directory, but can only be used to delete an empty directory.
- `rm`: lets you delete files and directories. Use `rm -r` to delete just the directory. It deletes both the folder and the files it contains when using only the `rm` command.
- `touch`: lets you create a new file e.g. `touch new_filename.txt`.
- `man`: lets you learn more about a command and see the ways in which it can be used e.g. `man cd`.
- `cp`: lets you copy files through the command line. It takes two arguments: The first is the location of the file to be copied, the second is where to copy e.g. `cp file.txt /home/folder`.
- `mv`: lets you move files through the command line. You can also use the `mv` command to rename a file e.g. to rename a file currently called file.txt to one called new_file.txt, simply write `mv file.txt new_file.txt`.
- `locate`: lets you locate a file in a Linux system, just like the search command in Windows. This command is useful when you don't know where a file is saved or the actual name of the file. Using the -i argument with the command helps to ignore the case (it doesn't matter if it is uppercase or lowercase). So, if you want a file that has the word “hello”, it gives the list of all the files in your Linux system containing the word "hello" when you type in `locate -i hello`.
- `echo`: lets you move some data, usually text into a file. For example, if you want to create a new text file or add to an already made text file, you just need to type in, `echo hello, my name is alok >> new.txt`.
- `cat`: lets you display the contents of a file. It is usually used to easily view programs.
- `nano`: nano is a pre-installed text editor in the Linux command line; it denotes keywords with color and can recognize most languages. If you need to make a new file named "check.txt", you can create it by using the command `nano check.txt`. You can save your files after editing by using the sequence Ctrl+X, then Y (or N for no).
- `sudo`: stands for "SuperUser Do". So, if you want any command to be done with administrative or root privileges, you can use the sudo command. For example, if you want to edit a file like base.conf (a configuration file), which needs root permissions, you can use the command – `sudo nano base.conf`.
- `apt-get`: lets you install packages. This requires root privileges, so you need to use the sudo command with it. For example, if you want to install a new package, you can type in the command `sudo apt-get install new_package_name`.
- `zip`: lets you compress files into a zip archive.
- `unzip`: lets you extract files from a zip archive.

A few tips and tricks for using the Linux CLI:

- You can use the `clear` command to clear the terminal if it gets filled up with too many commands.
- TAB can be used to auto-complete e.g. you just need to type `cd Doc` and then TAB and the terminal auto-completes to `cd Documents`.
- Ctrl+C can be used to stop any command in the terminal safely. If it doesn't stop with that, then Ctrl+Z can be used to force stop it.
- You can exit from the terminal by using the `exit` command.
- You can power off or reboot the computer by using the commands `sudo halt` and `sudo reboot`, respectively.
- Something extremely useful to set up is the quick-lauch shortcuts from the terminal for both VSCode and IntelliJ. These shortcuts allow you to navigate to a specific directory in your terminal and then launch the files in that folder using a one line command such as `code .` - for VSCode. That way there is no need to launch VSCode separately and open the files by navigating through the menus.

  - For VSCode, simply open the app, and press <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>p</kbd> , then type `shell`into the command palette. Select the option called "Shell Command : Install code in PATH" from the suggested list. That's it, from now on, you can simply navigate to your project directory in the terminal and type `code .` to have it open VSCode inside the project for you!

  <p align="center">
  <img src="images/vscode_ss1.png" alt="VSCode command line launcher" width="600"/>
  </p>

  - You are able to follow a similar process for setting up the command line launcher for IntelliJ; in that case, the command to launch the IDE is simply `idea .`. However, since you won't be needing that until you reach the Java section of the bootcamp, you can feel free to use this link at that time to guide you through the process: <https://emmanuelbernard.com/blog/2017/02/27/start-intellij-idea-command-line/> .

(Live Demo of a few commands at this point)

## Intro to Git: Setup and Basic Commands (35 mins)

- Conceptual intro: trees, branches, version control, benefits, collaboration - refer to slides.
  Will create/steal some diagrams from somewhere to explain this, then move onto the interactive demo
- Basic git commands - init, clone; diff, log, status; add, commit; checkout; branch, merge; push, pull
- Interactive demo: https://learngitbranching.js.org/ -- Ask questions to students: what do you think will happen if we do this?
- Git areas + stashing - could use some diagrams here

Now that you have a conceptual idea of how git works, lets start you off on getting to grips with some of the more practical applications of it.

**Creating a local git repository**

If you're creating a new project on your local machine using git, the first thing you'll do is create a new repository (aka "repo"). The first step will be to open a new terminal and move to the directory where you want your project folder to be saved, once there, you'll create your new project and then move inside of it.

<p align="center">
  <img src="images/terminal_ss1.png" alt="Create a new directory" width="600"/>
</p>

Once you're inside that folder, you'll want to initialise a git repository in the root of the folder by running the `git init` command.

<p align="center">
  <img src="images/terminal_ss2.png" alt="Initialise a repository" width="600"/>
</p>

\*Note: You can ignore the yellow warning message, it's simply informing you to run `git config --global init.defaultBranch whatever_name_you_want_here` so that in future all of your initial branches share the same desired name. The current naming convention is "master" in git, however theres is an ongoing debate regarding GitHub's recent decision to make their naming convention "main" for primary branches. You can read more about it at this link if you wish: <https://github.com/github/renaming>. However, for now, you might consider running the line `git config --global init.defaultBranch main` in order to supress this warning in future.

Now that you have a new repo initialised, you can go ahead and add a file to it using the `touch new_file_name.txt` command that creates and saves a blank file with whatever name you provide it. Referring back to the terminal commands in the previous section of this document, you'll see that you can type `ls` to a see a list of all files inside your current folder.

<p align="center">
  <img src="images/terminal_ss3.png" alt="Create a new file" width="600"/>
</p>

Once you've added or modified files in a folder containing a git repo, git will notice that the file exists inside the repo. But, git won't track the file unless you explicitly tell it to. Git only saves/manages changes to files that it tracks, so you’ll need to send a command to confirm that yes, you do want git to track your new file.

In order to see which files git recognises exist, you can run the `git status` command.

<p align="center">
  <img src="images/terminal_ss4.png" alt="See untracked files" width="600"/>
</p>

The response message in the screenshot above is basically informing you that git noticed there has been a new file created, but unless you use the `git add`command, git isn't going to do anything further with it - hence, it will be untracked.

The next step now is to add the file to the staging environment using the `git add .` command. You usually have to specify `git add name_of_file_here`, but if you add `.` instead, then it will add _all_ of your current untracked files to the staging area. If you now rerun the `git status` command, you'll see that git has added the file to the staging environment (beneath the "Changes to be committed" line).

<p align="center">
  <img src="images/terminal_ss5.png" alt="Add files to staging area" width="600"/>
</p>

At this point, the file has been added to the staging environment, but has **not yet been committed**. To create your commit, run the line `git commit -m "A message describing the changes made in your commit"` .

<p align="center">
  <img src="images/terminal_ss6.png" alt="Create commit" width="600"/>
</p>

**How to write a good commit message**

The message at the end of the commit should be something related to what the commit contains - maybe it's a new feature, maybe it's a bug fix, maybe it's just fixing a typo. Since this commit will likely be a permanent part of your repository, you must ensure that you leave a clear explanation of your changes as it can be extremely helpful for future programmers (perhaps future you!) who are trying to figure out why some change was made years later. Git is all about creating a legacy of code that is easily accessible!

Listed below are some general rules you should attempt to abide by when writing your own commit messages (source: https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/):

1. Specify the type of commit:
   feat: The new feature you're adding to a particular application
   fix: A bug fix
   style: Feature and updates related to styling
   refactor: Refactoring a specific section of the codebase
   test: Everything related to testing
   docs: Everything related to documentation
   chore: Regular code maintenance.[You can also use emojis to represent commit types]
2. Separate the subject from the body with a blank line
3. Your commit message should not contain any whitespace errors
4. Remove unnecessary punctuation marks
5. Do not end the subject line with a period
6. Capitalize the subject line and each paragraph
7. Use the imperative mood in the subject line
8. Use the body to explain what changes you have made and why you made them.
9. Do not assume the reviewer understands what the original problem was, ensure you add it.
10. Do not think your code is self-explanatory
11. Follow the commit convention defined by your team

A good example of the various components that you could possibly include in a commit message are shown below:

    `Capitalized, short (50 chars or less) summary

    More detailed explanatory text, if necessary.  Wrap it to about 72
    characters or so.  In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body.  The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together.

    Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
    or "Fixes bug."  This convention matches up with commit messages generated
    by commands like git merge and git revert.

    Further paragraphs come after blank lines.

    - Bullet points are okay, too

    - Typically a hyphen or asterisk is used for the bullet, followed by a
    single space, with blank lines in between, but conventions vary here

    - Use a hanging indent

    If you use an issue tracker, add a reference(s) to them at the bottom,
    like so:

    Resolves: #123 (This number or code could link to the card from your team's Kanban board that you are dealing with using the code in your commit)`

So far we've been working on a single branch, in this case that branch is main. The "main" branch - sometimes called "master" or "primary", is the branch with the latest, most-complete version of the project code, and it is usually the branch containing the deployed version of the code. But, if you wanted to add a new feature to your project and didn't want to run the risk of breaking the code on the main branch whilst in the development process for that new feature, then you will likely want to create a new git branch. Branches allow you to move back and forth between 'states' of a project. Once you're done with the page, you can merge your changes from your branch into the primary (main) branch. When you create a new branch, Git keeps track of which commit your branch 'branched' off of, so it knows the history behind all the files.

In order to create a new branch, you can run the command `git checkout -b name_of_branch_here`. This command will create the new branch and will then move you to that new branch (check you out there) so that you can immediately begin working on it. Once you've created the branch, you can see a list of all the branches currently in your repo by running the command `git branch`. The branch with `*` next to it denotes the branch you are currently working on.

<p align="center">
  <img src="images/terminal_ss7.png" alt="Create a new branch" width="600"/>
</p>

When you want to move to another branch that already exists, simply run `git checkout name_of_branch_here` (without the -b).

<p align="center">
  <img src="images/terminal_ss8.png" alt="Move to new branch" width="600"/>
</p>

Lastly, if you want to see a list, or history, of all the previous commits made to your project, then you can run `git log` . This will give you the details of the contributor, date/ time, and their commit message. We'll get into why this is can be useful later in this document.

<p align="center">
  <img src="images/terminal_ss9.png" alt="See commit history" width="600"/>
</p>

In terms of git commands that you would most likely use locally, I think we have covered them all at this point; the next stage is to now integrate what you have learned so far regarding git commands to the services offered by GitHub - that's where things become more useful!

## Intro to GitHub (60 mins)

If you haven't yet set up a GitHub account, you can do so using the following link: <https://github.com/signup>

Once you have created a GitHub account, the next step will be to add a new SSH key to your GitHub account. The SSH (Secure Shell) protocol is used so that you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can visit this link to add your SSH key (select the Linux tab once you're there):
<https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account>

Now that's done, you're ready to get going with using GitHub to make sharing your code easier than ever. Let's get started...

Firstly, you'll want to head to GitHub (<https://github.com/>) and log in with your newly created credentials.

**Creating a GitHub repo and linking it to your local repo**

To create a new repo on GitHub, navigate to the “New repository” option under the “+” sign next to your profile picture, in the top right corner of the navbar.

<p align="center">
  <img src="images/github_ss1.png" alt="New repo button" width="600"/>
</p>

You'll then just need to fill in the repository name (make this either the same name as your project, or something obvious and useful for your future collaborators to recognise). You'll have the option to make the repository either public or private - these options simply relate to who can view and commit to your repo. For now, just leave it as public since this will mean that you won't have to handle any permission or access issues for your any collaborators. It's useful to add a README file when initialising your repo since this is often used to provide any visitors to your repo a general overview of your project, the tech stack used, and maybe some instructions for accessing and using your code - but for now this will be just an empty template file.

<p align="center">
  <img src="images/github_ss2.png" alt="Create new repo" width="600"/>
</p>

GitHub will then ask if you want to create a new repo from scratch or if you want to add a repo you have created locally. In this case, since you've already created a new repo locally, you want to push that onto GitHub so follow the '....or push an existing repository from the command line' section of the prompt. That involves running the command `git remote add origin insert_web_url_to_repo_here`. The URL to your newly created repo can be accessed by clicking on the green code button on the home page of your repo as shown below:

<p align="center">
  <img src="images/github_ss3.png" alt="Copy repo url" width="600"/>
</p>

Now simply head back to the terminal and paste the url onto the end of the command mentioned in the previous paragraph to link your local repo to the GitHub one. You'll then want to run `git push -u origin master` in order to push a copy of your local master branch to the GitHub repo so that everyone else has access to your code too!

<p align="center">
  <img src="images/github_ss4.png" alt="Push to GitHub repo" width="600"/>
</p>

**Push branches with commits to GitHub**

Next 'll push the commit in your branch to your new GitHub repo. This allows other people to see the changes you've made. If they're approved by the repository's owner, the changes can then be merged into the primary branch.

To push changes onto a new branch on GitHub, you'll want to run `git push origin branch_name_here`. GitHub will automatically create the branch for you on the remote repository.

- merges
- pushing, pulling
- pull requests
- rebasing

## Live Demo Plan (screenshare) (15 mins)

One person creates a repo and shares the SSL link with the other person.
Other person uses terminal to clone the repo with the link.
That person creates a new branch locally, makes some changes and then goes through the add, commit, push process for that branch.
Original person pulls that branch locally and shows how to deal with merge conflicts and then pushes back to the origin.
Show a git log and git status and explain what's just happened between the two of us.

## Additional Features (10 mins)

- When you begin working on larger projects, you'll start to realise that there are 100's, if not 1000's of files, dependencies, and packages that are created as part of the scaffolding of your project e.g. when working node. However, you don't want your commits and pushes to GitHub getting inflated and overrun with files that don't need to be there (for example, every person working on your project will have node installed locally and can gain access to these files themselves without the need to pull them from Github). For that reason, GitHub has a an option to include a `.gitignore` file within your project; this is a text file that allows you to tell Git which files or folders you'd like to ignore in a project, and hence not have them committed each time. This file is normally placed in your project's root directory. In order to include one in your own project, simply create a file at the top level project folder and call it `.gitignore`, and within that file you can specify files to ignore in the following way:

<p align="center">
  <img src="images/gitignore_ss.png" alt=".gitignore example file" width="600"/>
</p>

- Another invaluable feature of GitHub is its integration with VSCode. VSCode has the LiveShare extension to allow you to collaborate with others on the same copy of the code (something you will become very accustomed to as time goes on), however to use this effectively, it is recommended that you log in to GitHub via VSCode beforehand to make sure that both accounts are synced. This will mean that the commit message from the LiveShare host will contain a section stating that you (your GitHub username) contributed to the commit in some way. Therefore, it is imperative that you log in to GitHub through VSCode at the outset to make collaboration and accountability go as smoothly as possible throughout the bootcamp. You can see an example of the contribution message below.

<p align="center">
  <img src="images/vscode_ss2.png" alt="github-vscode-liveshare integration" width="600"/>
</p>

- Trello/ GitHub Kanban section

### Kanban boards - brief aside

- A task-based project management style typically used in industry. Often used as a part of "sprints"
- A typical Kanban board would look something like this:

<p align="center">
    <img src="images/example-Kanban.png" alt="kanban board template" width="600">
</p>

- Tasks are given a ticket number, to keep track of what needs doing and when the problem arose and was solved. These ticket numbers would be referenced in any commits relating to the ticket
- Tickets are moved through the board as each task reaches a different stage. This is just a simple example board, but they can get a little more complex depending on size and scope of the project e.g. backlog, testing, design stage, deployment

- There are many companies, apps and programmes that have Kanbans as part of their setup for you to make. We're running through how to make them on GitHub, so they can be part of a code repository
- Is very easy to set up. Head to your GitHub repo that you want to create a board for and click 'Projects' at the top:

<p align="center">
    <img src="images/Github-Projects-example.png" alt="kanban board template" width="600">
</p>

- Follow the screen through, give your board a title and description
- Github gives you the option to choose from a number of templates, or just start blank and create your own accustomed to what you want. In the example shown is the basic Kanban template, which works well for simple projects:

<p align="center">
    <img src="images/Github-Projects-finished-setup.png" alt="kanban board template" width="600">
</p>

- discuss C/I and how GitHub can be used for it

## Into to GitHub Pages (45 mins?)

- You can use GitHub Pages to host a website about yourself, your organization, or your project directly from a GitHub repository.
- GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files through a build process, and publishes a website.
- You can host your site on GitHub's github.io domain or your own custom domain.
- There are three types of GitHub Pages sites: project, user, and organization. Project sites are connected to a specific project hosted on GitHub, such as a JavaScript library or a recipe collection. User and organization sites are connected to a specific GitHub account.
- GitHub Pages sites shouldn't be used for sensitive transactions like sending passwords or credit card numbers.
- Since the Github Pages service is free-to-use, there are some limitations to it:
  - Published GitHub Pages sites may be no larger than 1 GB
  - GitHub Pages sites have a soft limit of 10 builds per hour
    However, for your purposes at the start of this course, GitHub Pages is completely fine to use. Only later on, during larger projects, might you consider alternative hosting services that will better suit your requirements.

**Creating a Github Pages site**

- Steps for creating a GitHub pages website (which you will do as part of this afternoon's tasks) can be found in a well-documented, easy-to-follow manner at the following link: <https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site>

## EXERCISES (5 min)

**Part 1: Group exercise**

One person within your group should screenshare and go through the process to create a directory and local repo on their machine - with each person in the team taking a turn to talk through the next step that needs to be taken and explaining the purpose of that step.

Once the repo is created locally, that person will then open their GitHub account and step through the process for creating an online repository, again taking turns in having each person just make a comment on each step and making sure that everyone understands what exactly is going on.

Now that both the local Git repo, and the remote GitHub repo have been created, the host should head back to the terminal and go through the process to connect their local repo to the GitHub one, and then push the contents of their local repo.

The last stage in this exercise will be for the owner of the GitHub repo to share (copy and paste) the SSH link to the GitHub repo with the rest of the team.

**Part 2: Individual tasks (but still collaborating)**

Now that the GitHub repo is setup and ready to be used, each member of the team can fork and `clone` the repo for themselves onto their local machines.

Next, each person will create a new branch locally called `NAME_HERE_branch`. Each person will then add a new file to that branch called `NAME_HERE_new_file.txt` and will stage, then commit their work.

Then, each person should push _only_ their branch to the remote GitHub repo.

At this point, check in with your team and ensure that there are as many new branches as members of your team - you should all be able to see eachother's branches.

The last step will be for one person to begin screensharing again (doesn't have to be the same person as before), and then for that person to create a Pull Request for their new branch to the main branch. That person should select every other member of the team as reviewers for their PR. At this point, each member of the team should review the PR request, make a comment, and that branch should eventually be merged with the main branch.

By the end of this task, you will have a GitHub team repository that you have all contributed to by pushing from your local machines. This process replicates the one you will be doing over and over throughout the bootcamp.

**Part 3: Hosting your HTML/CSS project on GitHub Pages**

Following on from your work recently in HTML/ CSS, you are now asked to host your code so that others can benefit from the rendered version and get a flavour for what you have been working on. As mentioned earlier, this is a fairly standard process, and it will involve you visiting the link in the Intro to GitHub Pages section above and following the steps there very carefully. Once you have successfully completed all of the steps, feel free to share your project by copying and pasting the domain URL into the Discord server for all of your colleagues to see and appreciate. Well done, at this point you have just successfuly wrote and hosted your first static website!

## Additional Resources

- Git cheat sheet (downlaod and save locally here): <https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet>
- Git and GitHub Crash Course for beginners: <https://www.youtube.com/watch?v=SWYqp7iY_Tc>
- In-depth Git and GitHub for beginners done by Nelson (BNTA bootcamp trainer) on Amigoscode: <https://www.youtube.com/watch?v=3fUbBnN_H2c>
- Official Github docs: https://git-scm.com/
- Articles written by _Medium_ are highly recommended as they are concise and easy-to-follow, here are a couple of good ones related to Git:
  - <https://medium.com/@onejohi/git-understanding-the-basics-ba004a20dacc>
  - <https://medium.datadriveninvestor.com/the-complete-developers-guide-to-git-6a23125996e1>

## Check-in (3:30pm)

- Ask one or two students to screenshare their team's repo and explain what branches they created and merged.
- Ask if they had any issues or if they have any other questions in general.
- Personal/ Practical issues we ran into as a team when creating the BNTA App. How we solved them and what we would do differently.

## Sources

1. <https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners>
2. <https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/>
3. <https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners>
4. <https://www.freecodecamp.org/news/gitignore-what-is-it-and-how-to-add-to-repo/>
5. <https://frontendmasters.com/courses/git-in-depth/>
