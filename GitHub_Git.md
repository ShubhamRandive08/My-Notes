
# GitHub

What is GitHub?<br>
	It is tool that allows developers to store and manage their code using GIit.

		Link : https://github.com
		
1. Which folder upload on GitHub that is called as Repository and Repos.
2. If we want create the account on github then we should have one Gmail address.

How to create GitHub account : <br>
	1. Go on Google and search [https://github.com](https://github.com)
	2. Go on first link and click on Sign Up button
	3. Enter email
	4. Create Password and conform the Password
	5. Enter the username
	6. Verify the captha
	7. Click on 'Create account'
	8. Enter the OTP which sends on our Gmail
	9. Fill the details
	10. Successfully Created you Account

How to create the repository on GitHub?<br>
	 1. Go on right side profile tag and click on the repository section
	 2. Click on the NEW button 
	 3. Fill the some option like repos name, description, checkbox
	 4. Add README file (It is a markdown file. README file is a markdown file which is used for provide the extra information about the project and repos like use of project, need of project, projects feature and other related info.)
	 5. Click on Create Account Button

What is REAMDE file?<br>
	A **README** file in GitHub is a text file (usually written in **Markdown** format) that provides important information about a project. It typically serves as an introduction and guide for users and contributors. We can also use the html tag into the README file.

What is commit?<br>
	A **commit** in GitHub (and Git) is a snapshot of changes made to a repository at a particular point in time. It records modifications to files and allows you to track the history of changes over time.
	We can also provide the message for commit the changes

What is initial commit?<br>
	Initial commit means first change into the our repository.

# Git<br>

What is Git?<br>
	Git is a distributed version control system that allows multiple developers to collaborate on a project by tracking changes in the source code.
	-
	Which is used for the track the history and collaborate.

Adv. of the Git :<br>
	Offline capabilities
	Branching and merging
	Performance
	Popular
	Free and Open Source
	Fast and scalable

If we want to check Git is installed in our system or not file command : git --version<br>

![I](/Image/5644.png)


Hot to download  Git?<br>
	1. Go on google and search Git download
	2. Click on [https://git-scm.com/downloads](https://git-scm.com/downloads)
	3. Click on Download option
	4. When if download success then install it 

##### Note : There are two place Use Git which is local and Remote <br>

	
What is different type of Git commands?<br>

1. Configuration command :  git config     ( The purpose of the " git config " command is to configure and customize your Git environment. )<br>

		git config --global user.name "Your Name"
		git config --global user.email "srandive245@gmail.com"
		git config --list

2. Git snapshot command : git branch   (This command can be used for the manage branches in a Git repos. Branches allow you to work on different parts or features of a project independently )<br>

		List Branches :  
			git branch  - Lists all local branches in the repository.
			The current branch is marked with an asterisk(*)
		To include remote branches : 
			git branch -a

		Create a new branch :
			git branch < Branch-name >

		Delete a branch
			git branch -d < branch-name >

		Rename a branch 
			git branch -m < old name >  < new name >

		Show branch information
			git branch -v

		Find merged/unmerged branches 
			git branch --merged
			git branch --unmerged
			git clone <- cloning url ->


#### Git Clone and Status command :<br>
Clone - Cloning a repository on our local machine<br>
	    `git clone <- cloning url ->`
![](/Image/5353.png)

Status - Display the state of the code<br>
		 `git status`
1. Nothing to commit <br>
![](/Image/4856.png)


2. If we make some changes into the file <br>
![](/Image/0947.png)



###### Note : If we want the display the hidden file then fire command : `ls -a`
###### Note : If make changes into the file the follow following process --> 1. Adding changes 2. Commit the changes. There are four status for file :<br>
3. #untracked: New file that git doesn't yet track 

4. #modified : Changed file 

5. #staged : file is ready to be committed 

6. #unmodified : Unchanged file 

#### Add and Commit Command<br>
7. add - Adds new or changed files in your working directories to the git staging area.
     `git add < - File name - >` / `git add .` (For adding all changes file)
![](/Image/2527.png)


8. Commit - It is the record of change.<br>
     `git commit -m "Some message"`
	![](/Image/2907.png)


#### Push Command<br>
 push - It is used for upload local repo content to remote repo<br>
     `git push origin main`<br>
	 ![](/Image/3357.png)


 git push - That means i want to push our local code<br>
   
  
   ### Understanding  #origin in GitHub:<br>
9. origin - In GitHub (and Git in general), `origin` is the default name for the remote repository from which a local repository was cloned. It serves as a shorthand reference to the remote URL of the repository, making it easier to push and pull changes.

10. **When You Clone a Repository:<br>**
    
    - If you run:<br>
        bash<br>
        `git clone https://github.com/user/repo.git`<br>
        
    - Git automatically assigns the name `origin` to the remote repository (`https://github.com/user/repo.git`).<br>
11. **Viewing the Remote URL:<br>**
    - To check which remote repository is named `origin`, run:
        `git remote -v`
    - Example output:
        `origin  https://github.com/user/repo.git (fetch) origin  https://github.com/user/repo.git (push)`<br>
        
12. **Using `origin` in Commands:**<br>
    - **Pull changes from GitHub:**
        `git pull origin main`<br>
        
    - **Push changes to GitHub:**
        `git push origin main`<br>
        
13. **Changing or Adding a Remote URL:**<br>
    
    - If you need to change the `origin` URL:<br>
        `git remote set-url origin https://github.com/new-user/new-repo.git`<br>
        
    - To add a new remote (e.g., `upstream` for a forked repository):<br>
        `git remote add upstream https://github.com/original-repo.git`<br>

main - This is name of branch <br>

### init command : <br>
- Used to create the new git repository. And initialize the empty git.
   `git init` <br>
	![[Screenshot 2025-02-06 150440.png]]<br>

#### remote commands :<br>
- Git provides several `git remote` commands to manage remote repositories. Below is a list of commonly used Git remote commands along with their explanations.

- List all remote repositories <br>
     `git remote -v` <br>
	 ![](/Image/2703.png)<br>


- Show detailed information about the origin<br>
     `git remote show origin` <br>
	 ![](/Image/2827.png)<br>


- Add a new remote repository<br>
     `git remote add <remote_name> <remote_url>` <br>
	 Ex , `git remote add origin https://github.com/original/repo.git` <br>
     ![](/Image/3158.png)<br>


- Remove a remote repository<br>
     `git remote remove <remote_name>` <br>
	 Ex , `git remote remove upstream` <br>
     ![](/Image/3423.png)<br>


- Rename a remote<br>
     `git remote rename <old_name> <new_name>` <br>
	 Ex , `git remote rename origin github` <br>
     ![](/Image/3901.png)<br>



- Change the URL of remote <br>
     `git remote set-url <remote_name> <new_url>` <br>
	 Ex , `git remote set-url origin https://github.com/new-user/new-repo.git<br>

     ![MyImage](/Image/4143.png)<br>
`

- Fetch change from remote repos - Fetches updates **without merging** them into your working branch.<br>
     `git fetch <remote_name>` <br>
	 Ex , `git fetch origin` <br>
     ![](/Image/4646.png)<br>


- Pull changes from a remote repository - Fetches updates **and merges** them into your current branch.<br>
     `git pull <remote_name> <branch_name>` <br>
	 Ex , `git pull origin main` <br>
     ![](/Image/4750.png)<br>


- Push changes to a remote repository - Pushes your local commits to the remote repository.<br>
     `git push <remote_name> <branch_name>` <br>
	 Ex , `git push origin main` <br>
     ![](/Image/4203.png)<br>

- Prune deleted remote branches - Removes references to branches that no longer exist on the remote.<br>
     `git remote prune <remot<br>e_name>`  <br>
	 Ex , `git remote prune origin`<br>
     

- Check the default upstream branch - Shows the URL of the `origin` remote.<br>
     `git remote get-url origin`<br>

- Check all branches from a remote - Lists all remote branches.<br>
     `git branch -r`  <br>
#### Branching commands
- List all branches <br>
     `git branch`<br>
	 ![](/Image/4400.png)<br>


- List remote branches
     `git branch -r`<br>
	 ![](/Image/2058.png)<br>


- List all local & remote branches - - Shows both local and remote branches.<br>
     `git branch -a`<br>
	 ![](/Image/2135.png)


- Create new branch - This creates a new branch but does **not** switch to it.<br>
     `git branch <branch_name>`<br>
	 Ex , `git branch feature-login`<br>
	 ![](/Image/2224.png)<br>


- **Switch to a branch** (`checkout` method - older)
     `git checkout <branch_name
	 Ex , `git checkout feature-login`<br>
     ![](/Image/2324.png)<br>


- Create and switch to a new branch (`checkout -b` method - older)
     `git checkout -b <branch_name>`<br>
	 Ex , `git checkout -b feature-login`<br>
     ![](/Image/2454.png)<br>


- **Create and switch to a new branch** (`switch` method - recommended)<br>
     `git switch -c <branch_name>`<br>
	 Ex , `git switch -c feature-login`<br>
     ![](/Image/2538.png)<br>


- Delete a local branch<br>
     `git branch -d <branch_name>`<br>
	 Ex , `git branch -d feature-login`<br>
     ![](/Image/2811.png)<br>


- **Force delete a local branch** (use with caution!)<br>
     `git branch -D <branch_name>`<br>
	 Ex ,  `git branch -D feature-login`<br>
     ![](/Image/2926.png)<br>


- Delete a remote branch - This removes the branch from the remote repository.
     `git push origin --delete <branch_name>`<br>
	 Ex , `git push origin --delete feature-login`<br>
     

- Change the branch name<br>
     `git branch -M < Branch name >`<br>
	 Ex , `git branch -M main`<br>


- If we want don't re right the `origin main` then we use `-u` ( set upstream)  <br>
     `git push -u origin main`<br>
	 Ex ,  `git push -u origin main`<br>
    
### Merging and Rebasing<br>
- Merge a branch into the current branch<br>
     `git merge <branch_name>`<br>
	 Ex , `git merge feature-login`<br>

- Rebase a branch - Moves the current branch on top of the latest `main` branch changes.
     `git rebase <branch_name>`
	 Ex , `git rebase main`

#### Flow of the create repository

- GitHub Repositories
     - Clone the repository
         - Make changes in repos
             - Add the file
                 - Commit the changes
                     - Push the new file


    

Differentiate two branch
- `git diff < other branch name >`<br>
   Ex  ,  `git diff Shubham`<br>
   ![](/Image/1034.png)<br>


##### Merging Code commands<br>
- Way 1<br>
     - git diff <- branch name ->  To compare commits, branches, file and more<br>
     - git merge <- branch name ->  To merge two branches<br>

- Way 2<br>
     - Create a PR (Pull Request) - It lets you<br> tell others about changes you have pushed to a branch in a repository on GitHub.<br>
         - Go on GitHub and change the branch ignore main and click on pull requests<br>

##### Pull Requests :<br>
- It is used to fetch and download content from a remote repo and immediately update the local repo to match that content.<br>

     `git pull origin main`<br>
     ![](/Image/2804.png)<br>



##### Resolving Merge Conflicts<br>

- An events that takes place when Git is unable to automatically resolve differences in code between two commits.<br>

![](/Image/4900.png)<br>


Git command for Merge Conflic<br>

![](/Image/5044.png)



#### Undoing Changes<br>

- Case 1 :  Staged changes - Used for if we make the changes into the file but I don't make that changes and I only add this file and not commit then we will use `reset` command for undo the changes<br>
     `git reset <- file name ->`  -  for single file<br>
	 `git reset`  - for all files<br>

     ![](/Image/2321.png)<br>


- Case 2 : Commited changes (for one commit) - Undo the changes after one commit<br>
     `git reset HEAD ~ 1`<br>

- Case 3 : Commited changes (for many commits) - Undo the changes after many commits<br>
     `git reset < commit hash>`<br>
     `git reset --hard <- commit hash ->`<br>


`git log` - Used for check the log of commands <br>
---
ⓘ Metadata <br>
---
Title: My Note<br>
Tags:  #obsidian #notes #git #github<br>
Author : Shubham Randive<br>

---




