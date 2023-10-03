# Bash commands
##### [Generate ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
```bash
ssh-keygen -t ed25519 -C "github email"
```
##### Copy ssh key
```bash
clip < ~/.ssh/id_ed25519.pub
```
##### Remove local ssh key from root directory
```bash
cd
rm -r .ssh
```
##### Clone a repo from github
```bash
git clone git@github.com:mahfuz-prog/gitNgithub.git
git clone git@github.com:mahfuz-prog/gitNgithub.git .
```
##### Git config
```bash
git config --global core.autocrlf false
set username and email on repo
git config --global user.name "Username"
git config --global user.email "demo@gmail.com"
git config --list
```
##### Git initialize to push
```bash
git status
git init					
git add .				#stage
git reset				#remove everything from staging
git reset filename			#remove file from the staging area

git commit -m "Initial commit" 		#stage to commit	
git commit --amend -m 'commit title'	#to change commit title, Not to push this with other people
git branch -M main			#initialize the branch as main	
git remote add origin SSH key
echo "# afd" >> README.md		#add .md file
git push -u origin main
git clean -df				#remove all untract file
```
##### Branches
```bash
git branch
git branch -a 				#all branches local & remote
git branch branch-name			#create branch
git checkout branch-name 		#switch branch
git branch -m mew-name      #rename branch
git merge branch-name			#first switch main then marge branch-name
git push -u origin branch-name		#push remote
git branch -d branch-name 		#remove branch from local directory
git push origin --delete branch-name 	#delete from remote
```
##### Remote repository
```bash
git remote -v
git remote rm origin			#remove remote origin
```
##### Changes
```bash
git diff
git diff filename
git diff --staged filename		#Show edits in stage 
```
##### [Rules](https://gist.github.com/octocat/9257657)
```bash
touch .gitignore			#Create a .gitignore file
```
##### Recovery
```bash
git reflog
git checkout hash
git branch backup
```
