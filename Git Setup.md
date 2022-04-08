I find this resource extremely helpful: https://blog.reviewnb.com/github-jupyter-notebook/

The following is my experience setting up Git and GitHub to use Jupyter Notebook in Mac terminal. 
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
! First copy your one-time code: 74CC-03F1
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
