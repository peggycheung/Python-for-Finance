The following is my experience setting up Git and GitHub to use Jupyter Notebook in Mac terminal. 

### Setup

I find these resources extremely helpful: 
1. https://blog.reviewnb.com/github-jupyter-notebook/
2. https://docs.github.com/en/get-started/quickstart/hello-world

(Already installed *MacPorts* to use the `port` command in terminal.)


```console
Last login: Thu Apr  7 22:42:50 on ttys002
(base) wenpeizhang@Peggys-MBP ~ % sudo port install git
Password:
--->  Computing dependencies for git
The following dependencies will be installed: 
 bzip2
 curl
 curl-ca-bundle
...
 xz
 zlib
 zstd
Continue? [Y/n]: Y
--->  Fetching archive for curl-ca-bundle
--->  Attempting to fetch curl-ca-bundle-7.82.0_0.darwin_21.noarch.tbz2 from https://packages.macports.org/curl-ca-bundle
--->  Attempting to fetch curl-ca-bundle-7.82.0_0.darwin_21.noarch.tbz2.rmd160 from https://packages.macports.org/curl-ca-bundle
--->  Installing curl-ca-bundle @7.82.0_0
--->  Activating curl-ca-bundle @7.82.0_0
--->  Cleaning curl-ca-bundle
...
--->  No broken files found.
--->  No broken ports found.
...
(base) wenpeizhang@Peggys-MBP ~ % git config --global user.name "Peggy Cheung"
(base) wenpeizhang@Peggys-MBP ~ % git config --global user.email "peggy@example.com"
(base) wenpeizhang@Peggys-MBP ~ % sudo port install gh
--->  Fetching archive for gh
--->  Attempting to fetch gh-2.7.0_0.darwin_21.arm64.tbz2 from https://packages.macports.org/gh
--->  Attempting to fetch gh-2.7.0_0.darwin_21.arm64.tbz2.rmd160 from https://packages.macports.org/gh
--->  Installing gh @2.7.0_0
--->  Activating gh @2.7.0_0
--->  Cleaning gh
--->  Scanning binaries for linking errors
--->  No broken files found.
--->  No broken ports found.
(base) wenpeizhang@Peggys-MBP ~ % gh auth login
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser
! First copy your one-time code: 74CC-XXXX
Press Enter to open github.com in your browser... 
✓ Authentication complete.
- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as peggycheung
(base) wenpeizhang@Peggys-MBP ~ % git clone https://github.com/peggycheung/Python-for-Finance.git
Cloning into 'Python-for-Finance'...
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
(base) wenpeizhang@Peggys-MBP ~ % cp /Users/wenpeizhang/Documents/Udemy 2022/pp_Python for Finance_2.ipynb /Users/wenpeizhang/Python-for-Finance
cp: /Users/wenpeizhang/Documents/Udemy: No such file or directory
cp: 2022/pp_Python: No such file or directory
cp: for: No such file or directory
cp: Finance_2.ipynb: No such file or directory
(base) wenpeizhang@Peggys-MBP ~ % cp /Users/wenpeizhang/Documents/Udemy2022/pp_Python_for_Finance_2.ipynb /Users/wenpeizhang/Python-for-Finance
(base) wenpeizhang@Peggys-MBP ~ % git add pp_Python_for_Finance_2.ipynb
fatal: not a git repository (or any of the parent directories): .git
(base) wenpeizhang@Peggys-MBP ~ % /Users/wenpeizhang/Python-for-Finance
zsh: permission denied: /Users/wenpeizhang/Python-for-Finance
(base) wenpeizhang@Peggys-MBP ~ % cd /Users/wenpeizhang/Python-for-Finance
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git add pp_Python_for_Finance_2.ipynb
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   pp_Python_for_Finance_2.ipynb

(base) wenpeizhang@Peggys-MBP Python-for-Finance % git commit -m "Add my second jupyter notebook - starting with section 11"                 
[main 5fe7cea] Add my second jupyter notebook - starting with section 11
 1 file changed, 77 insertions(+)
 create mode 100644 pp_Python_for_Finance_2.ipynb
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 10 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.01 KiB | 1.01 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/peggycheung/Python-for-Finance.git
   01d4bf5..5fe7cea  main -> main
(base) wenpeizhang@Peggys-MBP Python-for-Finance % 

```
---

### Use Git to push changes to GitHub

Resources:
1. https://www.freecodecamp.org/news/pushing-to-github-made-simple-enough-for-poets/
2. https://stackoverflow.com/questions/24114676/git-error-failed-to-push-some-refs-to-remote

**Initiate Git**

```console
(base) wenpeizhang@Peggys-MBP ~ % git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /Users/wenpeizhang/.git/

```
**Locate the repository that I have on my local machine**
```console
(base) wenpeizhang@Peggys-MBP ~ % cd /Users/wenpeizhang/Python-for-Finance
```

**Track any changes made to the folder on your system, since the last commit.**
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git add pp_Python_for_Finance_2.ipynb
```

See Git Status: It shows that pp_Python_for_Finance_2.ipynb has been modified
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   pp_Python_for_Finance_2.ipynb
```
**Prepare the added/tracked changes to the folder on my local machine for pushing to Github and add commit messages/comment**
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git commit -m "Completed section 11, 60-69"
[main cfb9362] Completed section 11, 60-69
 1 file changed, 1941 insertions(+), 3 deletions(-)
```
**Push changes to GitHub. (Note that the last word in the command master, is not a fixed entry when running git push. It can be replaced with any relevant “branch_name”).**
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git push
```
**Encountered an error -- this is because the GitHub repo has seen new commits pushed to it and the repository on my local machine is not up to date.**
```console
To https://github.com/peggycheung/Python-for-Finance.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/peggycheung/Python-for-Finance.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
**Then we need to first pull then push to update repository folder on our local machine**
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git pull --rebase origin main
From https://github.com/peggycheung/Python-for-Finance
 * branch            main       -> FETCH_HEAD
Successfully rebased and updated refs/heads/main.
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 10 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 227.21 KiB | 15.15 MiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/peggycheung/Python-for-Finance.git
   6148c9f..b9e711b  main -> main
```
**Check Git status to make sure changes are pushed to Github**
```console
(base) wenpeizhang@Peggys-MBP Python-for-Finance % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) wenpeizhang@Peggys-MBP Python-for-Finance % 

```
**Push an img folder to Github so it can display the image in jupyter notebook**
1. Copy and paste the image folder to the corresponding repository folder on the local machine

It is assumed, that you have the following file structure and that you run the jupyter notebook command in the directory where the file example.ipynb (<-- contains the markdown for the image) is stored:
```
+-- example.ipynb
+-- img
    +-- picture.png
```
In this case, in my `CFA-I` repository folder it is:
```
+-- Quantitative_Methods.ipynb
+-- img
    +-- flowchart_select_viz.jpg
```
2. Run the following in terminal
```console
(base) wenpeizhang@Peggys-MBP CFA-I % git add .      
(base) wenpeizhang@Peggys-MBP CFA-I % git commit -m "add a img folder"
[main 169f300] add a img folder
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .DS_Store
 create mode 100644 img/.DS_Store
 create mode 100644 img/flowchart_select_viz.jpg
(base) wenpeizhang@Peggys-MBP CFA-I % git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 10 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 744.08 KiB | 26.57 MiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/peggycheung/CFA-I.git
   a8c231a..169f300  main -> main
```
