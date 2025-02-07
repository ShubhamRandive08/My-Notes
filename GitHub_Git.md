
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

![[Pasted image 20250206095657.png]]


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
![[Pasted image 20250206105414.png]]

Status - Display the state of the code<br>
		 `git status`
1. Nothing to commit <br>
![[Pasted image 20250206104908.png]]

1. If we make some changes into the file <br>
![[Pasted image 20250206111014.png]]


###### Note : If we want the display the hidden file then fire command : `ls -a`
###### Note : If make changes into the file the follow following process --> 1. Adding changes 2. Commit the changes. There are four status for file :<br>
1. untracked : New file that git doesn't yet track 

2. modified : Changed file 

3. staged : file is ready to be committed 

4. unmodified : Unchanged file 

#### Add and Commit Command<br>
5. add - Adds new or changed files in your working directories to the git staging area.
     `git add < - File name - >` / `git add .` (For adding all changes file)
![[Pasted image 20250206122538.png]]

6. Commit - It is the record of change.<br>
     `git commit -m "Some message"`
	![[Pasted image 20250206122919.png]]

#### Push Command<br>
 push - It is used for upload local repo content to remote repo<br>
     `git push origin main`
	 ![[Pasted image 20250206123422.png]]

 git push - That means i want to push our local code<br>
   
  
   ### Understanding  origin in GitHub:<br>
1. origin - In GitHub (and Git in general), `origin` is the default name for the remote repository from which a local repository was cloned. It serves as a shorthand reference to the remote URL of the repository, making it easier to push and pull changes.

2. **When You Clone a Repository:<br>**
    
    - If you run:<br>
        bash<br>
        `git clone https://github.com/user/repo.git`
        
    - Git automatically assigns the name `origin` to the remote repository (`https://github.com/user/repo.git`).
3. **Viewing the Remote URL:<br>**
    - To check which remote repository is named `origin`, run:
        `git remote -v`
    - Example output:
        `origin  https://github.com/user/repo.git (fetch) origin  https://github.com/user/repo.git (push)`
        
4. **Using `origin` in Commands:**<br>
    - **Pull changes from GitHub:**
        `git pull origin main`
        
    - **Push changes to GitHub:**
        `git push origin main`
        
5. **Changing or Adding a Remote URL:**<br>
    
    - If you need to change the `origin` URL:<br>
        `git remote set-url origin https://github.com/new-user/new-repo.git`
        
    - To add a new remote (e.g., `upstream` for a forked repository):<br>
        `git remote add upstream https://github.com/original-repo.git`

main - This is name of branch <br>

### init command : <br>
- Used to create the new git repository. And initialize the empty git.
   `git init` <br>
	![[Pasted image 20250206150457.png]]

#### remote commands :<br>
- Git provides several `git remote` commands to manage remote repositories. Below is a list of commonly used Git remote commands along with their explanations.

- List all remote repositories <br>
     `git remote -v` <br>
	 ![[Pasted image 20250206152741.png]]

- Show detailed information about the origin<br>
     `git remote show origin` <br>
	 ![[Pasted image 20250206152845.png]]

- Add a new remote repository<br>
     `git remote add <remote_name> <remote_url>` <br>
	 Ex , `git remote add origin https://github.com/original/repo.git` <br>
     ![[Pasted image 20250206153311.png]]

- Remove a remote repository<br>
     `git remote remove <remote_name>` <br>
	 Ex , `git remote remove upstream` <br>
     ![[Pasted image 20250206153433.png]]

- Rename a remote<br>
     `git remote rename <old_name> <new_name>` <br>
	 Ex , `git remote rename origin github` <br>
     ![[Pasted image 20250206153917.png]]

- Change the URL of remote <br>
     `git remote set-url <remote_name> <new_url>` <br>
	 Ex , `git remote set-url origin https://github.com/new-user/new-repo.git
     ![[Pasted image 20250206154158.png]]
`

- Fetch change from remote repos - Fetches updates **without merging** them into your working branch.<br>
     `git fetch <remote_name>` <br>
	 Ex , `git fetch origin` <br>
     ![[Pasted image 20250206154657.png]]

- Pull changes from a remote repository - Fetches updates **and merges** them into your current branch.<br>
     `git pull <remote_name> <branch_name>` <br>
	 Ex , `git pull origin main` <br>
     ![[Pasted image 20250206154804.png]]

- Push changes to a remote repository - Pushes your local commits to the remote repository.<br>
     `git push <remote_name> <branch_name>` <br>
	 Ex , `git push origin main` <br>
     ![[Pasted image 20250206184221.png]]

- Prune deleted remote branches - Removes references to branches that no longer exist on the remote.<br>
     `git remote prune <remot<br>e_name>`  <br>
	 Ex , `git remote prune origin`
     

- Check the default upstream branch - Shows the URL of the `origin` remote.<br>
     `git remote get-url origin`

- Check all branches from a remote - Lists all remote branches.<br>
     `git branch -r`  <br>
<<<<<<< HEAD
##### NOTE : If we want to fetch the remote repos into the local repos then we are file following commands,
	`git fetch origin`


Differentiate two branch
- `git diff < other branch name >`<br>
   Ex  ,  `git diff Shubham`<br>
   ![[Pasted image 20250206231056.png]]

##### Merging Code commands<br>
- Way 1<br>
     - git diff <- branch name ->  To compare commits, branches, file and more
     - git merge <- branch name ->  To merge two branches

- Way 2<br>
     - Create a PR (Pull Request) - It lets you<br> tell others about changes you have pushed to a branch in a repository on GitHub.
         - Go on GitHub and change the branch ignore main and click on pull requests

##### Pull Requests :<br>
- It is used to fetch and download content from a remote repo and immediately update the local repo to match that content.<br>

     `git pull origin main`<br>
     ![[Pasted image 20250206232818.png]]


##### Resolving Merge Conflicts<br>

- An events that takes place when Git is unable to automatically resolve differences in code between two commits.<br>

![[Pasted image 20250206234910.png]]

Git command for Merge Conflic<br>

![[Pasted image 20250206235056.png]]


#### Undoing Changes<br>

- Case 1 :  Staged changes - Used for if we make the changes into the file but I don't make that changes and I only add this file and not commit then we will use `reset` command for undo the changes<br>
     `git reset <- file name ->`  -  for single file<br>
	 `git reset`  - for all files<br>

     ![[Pasted image 20250207002344.png]]


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



=======
#### Branching commands
- List all branches 
     `git branch`
	 ![[Pasted image 20250206221925.png]]

- List remote branches
     `git branch -r`
	 ![[Pasted image 20250206222108.png]]

- List all local & remote branches - - Shows both local and remote branches.
     `git branch -a`
	 ![[Pasted image 20250206222147.png]]

- Create new branch - This creates a new branch but does **not** switch to it.
     `git branch <branch_name>`
	 Ex , `git branch feature-login`
	 ![[Pasted image 20250206222235.png]]

- **Switch to a branch** (`checkout` method - older)
     `git checkout <branch_name
	 Ex , `git checkout feature-login`
     ![[Pasted image 20250206222334.png]]

- Create and switch to a new branch (`checkout -b` method - older)
     `git checkout -b <branch_name>`
	 Ex , `git checkout -b feature-login`
     ![[Pasted image 20250206222503.png]]

- **Create and switch to a new branch** (`switch` method - recommended)
     `git switch -c <branch_name>`
	 Ex , `git switch -c feature-login`
     ![[Pasted image 20250206222549.png]]

- Delete a local branch
     `git branch -d <branch_name>`
	 Ex , `git branch -d feature-login`
     ![[Pasted image 20250206222821.png]]

- **Force delete a local branch** (use with caution!)
     `git branch -D <branch_name>`
	 Ex ,  `git branch -D feature-login`
     ![[Pasted image 20250206222949.png]]

- Delete a remote branch - This removes the branch from the remote repository.
     `git push origin --delete <branch_name>`
	 Ex , `git push origin --delete feature-login`
     

- Change the branch name
     `git branch -M < Branch name >`
	 Ex , `git branch -M main`
     ![[Pasted image 20250206214517.png]]

- If we want don't re right the `origin main` then we use `-u` ( set upstream)  
     `git push -u origin main`
	 Ex ,  `git push -u origin main`
      ![[Pasted image 20250206220829.png]]
### Merging and Rebasing
- Merge a branch into the current branch
     `git merge <branch_name>`
	 Ex , `git merge feature-login`

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


    
>>>>>>> main
