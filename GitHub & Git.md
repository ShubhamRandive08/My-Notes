
What is Git?

Git is a distributed version control system that allows multiple developers to collaborate on a project by tracking changes in the source code.


Adv. of the Git :
	Offline capabilities
	Branching and merging
	Performance

What is different type of Git commands?
1. Configuration command :  git config     ( The purpose of the " git config " command is to configure and customize your Git environment. )

		git config --global user.name "Your Name"
		git config --global user.email "srandive245@gmail.com"

2. Git snapshot command : git branch   (This command can be used for the manage branches in a Git repos. Branches allow you to work on different parts or features of a project independently )

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
	

	