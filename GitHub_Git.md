
# GitHub

What is GitHub?
	It is tool that allows developers to store and manage their code using GIit.

		Link : https://github.com
		
1. Which folder upload on GitHub that is called as Repository and Repos.
2. If we want create the account on github then we should have one Gmail address.

How to create GitHub account : 
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

How to create the repository on GitHub?
	 1. Go on right side profile tag and click on the repository section
	 2. Click on the NEW button 
	 3. Fill the some option like repos name, description, checkbox
	 4. Add README file (It is a markdown file. README file is a markdown file which is used for provide the extra information about the project and repos like use of project, need of project, projects feature and other related info.)
	 5. Click on Create Account Button

What is REAMDE file?
	A **README** file in GitHub is a text file (usually written in **Markdown** format) that provides important information about a project. It typically serves as an introduction and guide for users and contributors. We can also use the html tag into the README file.

What is commit?
	A **commit** in GitHub (and Git) is a snapshot of changes made to a repository at a particular point in time. It records modifications to files and allows you to track the history of changes over time.
	We can also provide the message for commit the changes

What is initial commit?
	Initial commit means first change into the our repository.

# Git

What is Git?
	Git is a distributed version control system that allows multiple developers to collaborate on a project by tracking changes in the source code.
	-
	Which is used for the track the history and collaborate.

Adv. of the Git :
	Offline capabilities
	Branching and merging
	Performance
	Popular
	Free and Open Source
	Fast and scalable

If we want to check Git is installed in our system or not file command : git --version

![[Pasted image 20250206095657.png]]


Hot to download  Git?
	1. Go on google and search Git download
	2. Click on [https://git-scm.com/downloads](https://git-scm.com/downloads)
	3. Click on Download option
	4. When if download success then install it 

##### Note : There are two place Use Git which is local and Remote 

	
What is different type of Git commands?

2. Configuration command :  git config     ( The purpose of the " git config " command is to configure and customize your Git environment. )

		git config --global user.name "Your Name"
		git config --global user.email "srandive245@gmail.com"
		git config --list

3. Git snapshot command : git branch   (This command can be used for the manage branches in a Git repos. Branches allow you to work on different parts or features of a project independently )

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


#### Git Clone and Status command :
Clone - Cloning a repository on our local machine
	    `git clone <- cloning url ->`
![[Pasted image 20250206105414.png]]

Status - Display the state of the code
		 `git status`
1. Nothing to commit 
![[Pasted image 20250206104908.png]]

2. If we make some changes into the file 
![[Pasted image 20250206111014.png]]


###### Note : If we want the display the hidden file then fire command : `ls -a`
###### Note : If make changes into the file the follow following process --> 1. Adding changes 2. Commit the changes. There are four status for file :
1. #untracked: New file that git doesn't yet track 

2. #modified : Changed file 

3. #staged : file is ready to be committed 

4. #unmodified : Unchanged file 

#### Add and Commit Command
1. add - Adds new or changed files in your working directories to the git staging area.
     `git add < - File name - >` / `git add .` (For adding all changes file)
![[Pasted image 20250206122538.png]]

2. Commit - It is the record of change.
     `git commit -m "Some message"`
	![[Pasted image 20250206122919.png]]

#### Push Command
 push - It is used for upload local repo content to remote repo
     `git push origin main`
	 ![[Pasted image 20250206123422.png]]

 git push - That means i want to push our local code
   
  
   ### Understanding  #origin in GitHub:
1. origin - In GitHub (and Git in general), `origin` is the default name for the remote repository from which a local repository was cloned. It serves as a shorthand reference to the remote URL of the repository, making it easier to push and pull changes.

2. **When You Clone a Repository:**
    
    - If you run:
        bash
        `git clone https://github.com/user/repo.git`
        
    - Git automatically assigns the name `origin` to the remote repository (`https://github.com/user/repo.git`).
3. **Viewing the Remote URL:**
    - To check which remote repository is named `origin`, run:
        `git remote -v`
    - Example output:
        `origin  https://github.com/user/repo.git (fetch) origin  https://github.com/user/repo.git (push)`
        
4. **Using `origin` in Commands:**
    - **Pull changes from GitHub:**
        `git pull origin main`
        
    - **Push changes to GitHub:**
        `git push origin main`
        
5. **Changing or Adding a Remote URL:**
    
    - If you need to change the `origin` URL:
        `git remote set-url origin https://github.com/new-user/new-repo.git`
        
    - To add a new remote (e.g., `upstream` for a forked repository):
        `git remote add upstream https://github.com/original-repo.git`

main - This is name of branch 

### init command : 
- Used to create the new git repository. And initialize the empty git.
   `git init`
	![[Pasted image 20250206150457.png]]

#### remote commands :
- Git provides several `git remote` commands to manage remote repositories. Below is a list of commonly used Git remote commands along with their explanations.

- List all remote repositories 
     `git remote -v`
	 ![[Pasted image 20250206152741.png]]

- Show detailed information about the origin
     `git remote show origin`
	 ![[Pasted image 20250206152845.png]]

- Add a new remote repository
     `git remote add <remote_name> <remote_url>`
	 Ex , `git remote add origin https://github.com/original/repo.git`
     ![[Pasted image 20250206153311.png]]

- Remove a remote repository
     `git remote remove <remote_name>`
	 Ex , `git remote remove upstream`
     ![[Pasted image 20250206153433.png]]

- Rename a remote
     `git remote rename <old_name> <new_name>`
	 Ex , `git remote rename origin github`
     ![[Pasted image 20250206153917.png]]

- Change the URL of remote 
     `git remote set-url <remote_name> <new_url>`
	 Ex , `git remote set-url origin https://github.com/new-user/new-repo.git
     ![[Pasted image 20250206154158.png]]
`

- Fetch change from remote repos - Fetches updates **without merging** them into your working branch.
     `git fetch <remote_name>`
	 Ex , `git fetch origin`
     ![[Pasted image 20250206154657.png]]

- Pull changes from a remote repository - Fetches updates **and merges** them into your current branch.
     `git pull <remote_name> <branch_name>`
	 Ex , `git pull origin main`
     ![[Pasted image 20250206154804.png]]

- Push changes to a remote repository - Pushes your local commits to the remote repository.
     `git push <remote_name> <branch_name>`
	 Ex , `git push origin main`
     ![[Pasted image 20250206184221.png]]

- Prune deleted remote branches - Removes references to branches that no longer exist on the remote.
     `git remote prune <remote_name>`
	 Ex , `git remote prune origin`
     

- Check the default upstream branch - Shows the URL of the `origin` remote.
     `git remote get-url origin`

- Check all branches from a remote - Lists all remote branches.
     `git branch -r`