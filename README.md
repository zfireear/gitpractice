#### clone the project
git clone https://github.com/zfireear/gitpractice.git

#### (option)create a master branch,default is main branch
git branch -M master
### track remote
git remote add origin https://github.com/zfireear/gitpractice.git

### check the branch
git branch -vv 
- -r : to see remote branches
- -a : to see all local and remote branches

#### (optional) change the branch name
##### old-branch-name: main
##### new-branch-name: master
git branch -m old-branch-name new-branch-name
#### (optional) delete remote branch
git push origin --delete old-branch-name
#### (optional) push renamed branch to remote
git push origin -u new-branch-name
#### (optional) delet local branch
git branch -d local-branch-name

## git flow Process

### 1.checkout latest master branch
git checkout master

### 2.pull latest master branch
git pull

### 3.create a new branch for feature or bugfix from master branch
git checkout -b feature/BCE-XXX or bugfix/BCE-XXX

### if branch existed, switch to a branch in your local repo
git checkout feature/BCE-XXX or bugfix/BCE-XXX

### add and commit your change
git add .
git commit -m "add xxx"

### 4.test your feature or bugfix, if work well, push to remote
git push origin feature/BCE-XXX or bugfix/BCE-XXX
### if the upstream branch is not already created,run the command with the “-u” option

#### (optional) if you failed to push, run the follow command
git push --set-upstream origin feature/BCE-XXX

### 5.checkout to BCE/staging if the feature/bugfix is completed within the regression test
git checkout BCE/staging

### 6.pull the latest changes
git pull

### 7.merge the completed feature/bugfix branch into BCE/staging
git merge --squash feature/BCE-XXX or bugfix/BCE-XXX

### 8.commit the merge changes into BCE/staging branch
git commit -m "Merge 'feature/BCE-XXX' or 'bugfix/BCE-XXX' branch into 'BCE/staging'"

### 9.push the changes in BCE/staging branch to remote
git push origin BCE/staging


