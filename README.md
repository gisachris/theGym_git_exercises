## <div align='center'>GIT LEARNING</div>

> This repository is used for git learning and exercises


### <div align='center'>TABLE OF CONTENTS</div>
- [Document Schematic](#document-schematic)
- [Bundle One](#bundle-one)
  - [Exercise One](#exercise-one)
  - [Exercise Two](#exercise-two)

## Document Schematic
> Below are some of the keyWords and interpretations of the code written below.

`user#`: This means thta that line of code is written in the console.<br>

`>`: This will represent the Output of a given Command.

## Bundle One
### Exercise One()
> Below are the exercise Question criteria
1. Create a project folder & initialize git
2. Make changes to the project (add files and contents)
3. Rename your main branch from `master` to `main` (If your branch name is already `main` then rename it to `master` and then back to `main`)
4. Stage your changes and commit them
5. Create a Github repo and connect it with your project
6. Push your changes to GitHub
7. Create a new branch `dev`
8. From `dev` create another branch `test`
9. Go back to the `dev` branch and delete the `test` branch

> below are the solution steps.

1. Create a project folder & initialize git
```
user# mkdir proj_one

user# cd proj_one

user# git init

> Initialized empty Git repository in /Users/gymagasaro/Desktop/git_learning/projects/proj_one/.git/
```
2. Make changes to the project (add files and contents)
4. Stage your changes and commit them
```
user# touch page.md

user# touch .keep

user# git add .

user# git commit -m "project first commit"

> [main (root-commit) a512875] project first commit
    2 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 .keep
    create mode 100644 page.md
```

4. Rename your main branch from `master` to `main` (If your branch name is already `main` then rename it to `master` and then back to `main`)
```
user# git branch

> main

user# git branch -m master

user# git branch

> master

user# git branch -m main

user# git branch

> main
```
5. Create a Github repo and connect it with your project
6. Push your changes to GitHub
```
user# git remote add origin git@github.com:gisachris/git_project_one.git

user# git push -u origin main

> Enumerating objects: 3, done.
    Counting objects: 100% (3/3), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 242 bytes | 242.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    To github.com:gisachris/git_project_one.git
     * [new branch]      main -> main
    branch 'main' set up to track 'origin/main'.
```
7. Create a new branch `dev`
```
user# git checkout -b dev

> Switched to a new branch 'dev'

user# git branch

>   * dev
    main
```
8. From `dev` create another branch `test`
```
user# git checkout -b test

> Switched to a new branch 'test'

user# git branch

>   dev
    main
    * test
```
9. Go back to the `dev` branch and delete the `test` branch
```
user# git checkout dev

> Switched to branch 'dev'

user# git branch -d test

> Deleted branch test (was a512875).

user# git branch

>    * dev
     main
```
