#GIT Basics:
#1. First time setting up git on your system
    git config --global user.name "YOUR NAME"
    git config --global user.email "YOUR EMAIL ADDRESS"

#2. To clone the repository
    git clone "remote repository"
    git clone --bare "remote repository" #-> This command will create bare repository and you won't get the working tree 

#3. To list the branches
    git branch -l  #-> For Local
    git branch -r [-vv] #-> For remote repositories (-vv with more details)
    git branch -vv  #-> To list the mapping betwenn remote and local branches
   
#4. To list all the branches and tags that are generated in remote repository
    git ls-remote

#5. To create/delete branch
    #Create:
    git branch "branchname"
    
    #Delete:
    git branch -d "branchname"
	  git branch -D "branchname" #-> Force the deletion
	  
#6. To create local branch and link with the remote branch
    git checkout -b "branchname" "origin/remotebranch"  #-> This command will switch the current working tree to 
                                                              newly created branch name
    git checkout "Branch/master" #-> Branch/master to which the current working tree switch to
    
#7. Run following command to check the current active branch with marking "*".
    git branch  #-> The active branch will always be highlighte in different color and marked "*"
    
#8. To clean all untracked files and directories
	  git clean -f #-> only files
	  git clean -d #-> only directories
	  git clean -fd #-> Both files and directories 
	  
#9. To checkout remote tags
    git checkout tags/<tag-version> -b <Local branch name>
    #EX:
      git checkout tags/v4.4-rc4 -b linux-4.4-rc4  #-> In general the branch name must not be similar to the tag version to avoid 
                                                      the confusion between branch and tag
#10. To merge the newer changes commit back to older kernel version
	git merge #<commithash>  #-> Merge all the changes/commits up to the provided commit hash
	git cherry-pick #<commithash>  #-> Merge only the povided commit change on top of the current commit.
	
