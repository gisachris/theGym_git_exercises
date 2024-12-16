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

cd proj_one

git init

> Initialized empty Git repository in /Users/gymagasaro/Desktop/git_learning/projects/proj_one/.git/
```
2. Make changes to the project (add files and contents)
```
touch page.md

touch .keep

git add .

git commit -m "project first commit"

> [main (root-commit) a512875] project first commit
    2 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 .keep
    create mode 100644 page.md
```

3. Rename your main branch from `master` to `main` (If your branch name is already `main` then rename it to `master` and then back to `main`)
```
git branch

> main

git branch -m master

git branch

> master

git branch -m main

git branch

>main
```
