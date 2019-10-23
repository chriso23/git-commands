Git Commands
------------

The following content contains a reference document that demonstrates how to execute the most common Git commands using the command-line.

### Upload files from a local directory to a new Git repository

If you have a project on your local computer and you created an new Git repository on GitHub, you can use the following commands to quickly upload your project to your new Git repository on GitHub:

```bash
cd your-directory
git init
git remote add origin git@github.com:your-username/your-repo.git
git add .
git commit -am "Message"
git push -u origin master
```

### Download all files from a Git repository to a local directory

To download a repository from a Git repository to a local directory, run the following command:

```bash
git clone https://github.com/your-username/your-repo.git # using HTTPS
```

### Remove one file from Git cache

To remove one cached file, run this command:

```bash
git rm -r —-cached file.txt
```

### Override an entire local directory

If you have to resolve any merge conflicts in your project's local directory, you can use the following commands to override all local changes to your project; as such, this subsequently allows you to pull from the master from your Git repository.

```bash
git fetch --all
git reset --hard origin/master
```

### Force a push or pull

To allow your local directory to override the remote Git repository, you can run these two commands:

```bash
git push -f origin master
git pull -f origin master
```

### Merging changes from remote pull request with conflicts

1. To make a new branch with their changes.

```bash
git checkout -b their-branch master
git pull their.git master
```

2. Create a file from your local directory and commit those changes to your Git repository.   

```bash
git add files
git commit -m “Message"
git push origin master
```

3. Merge back into your branch.  

```bash
git checkout master
git merge --no-ff <their-branch) (:wq!)
git push origin master
```

### Remove branch (local & remote repositories) 

To remove a branch from a local directory or remote repository, use the following commands:

```bash
git push origin :branch-name
```

Use `--delete` or `-D` for local.

```
git branch --delete branch-name
````

### Replace master branch with the contents of another branch

```bash
git checkout branch-name
git merge -s ours master
git checkout master
git merge branch-name
```

### Remove all local branches except the master branch

```bash
git branch | grep -v "master" | xargs git branch -D
```

More than one branch may be added to the grep. To remove all local branches except "master" and "develop":

```bash
git branch | grep -v "master\|develop" | xargs git branch -D
```

 ### Allow empty commits
 
To allow empty commits, run the following commands:

 ```bash
 git push production master
 git commit --allow-empty -m 'push to execute post-receive'
 git push production master
 ```
 
 ### Merge new-feature branch into the master branch

```bash
git checkout master
git pull origin master
git merge new-feature
git push origin master
```

### Fetch a branch from its origin

```bash
git fetch origin
git checkout --track origin/<remote_branch_name>
```

### Accept all incoming changes

```bash
git pull -Xtheirs
```

### How to rebase from origin/develop

```bash
git fetch --prune --all
git rebase origin/develop
git pull
git push
```

### Stashing

Use stashing to save and archive local changes from one branch so that you can switch to another branch.

```bash
git stash
git checkout -b new-branch
git stash pop
```

### GitHub pages to non-docs folder

```bash
git subtree push --prefix dist origin gh-pages
```

License
-------
[MIT License](https://github.com/chrisoung/git-commands/blob/master/LICENSE).
