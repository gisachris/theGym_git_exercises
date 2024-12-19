## <div align='center'>GIT LEARNING</div>

> This repository is used for git learning and exercises


### <div align='center'>TABLE OF CONTENTS</div>
- [Document Schematic](#document-schematic)
- [Bundle One](#bundle-one)
  - [Exercise One](#exercise-one)
  - [Exercise Two](#exercise-two)
- [Bundle Two](#bundle-two)
  - [Exercise One](#exercise-one)
  - [Exercise Two](#exercise-two)

## Document Schematic
> Below are some of the keyWords and interpretations of the code written below.

`user#`: This means thta that line of code is written in the console.<br>

`>`: This will represent the Output of a given Command.

## Bundle One
### Exercise One
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
<br>
<br>

---
### Exercise Two
1. Create a new `home.html` file, add some html changes and save them
2. Stash save your current changes
3. Repeat the same process for a new `about.html` page and stash save your changes
4. Repeat the same process for a new `team.html` page and stash save your changes
5. Using stash pop restore the changes of the `about.html` page
6. With the help of an index use stash pop bring back the `home.html` page changes
7. Commit the current changes and push them
8. Using stash pop restore the changes of the `team.html` page index
9. Reset the current changes using git reset and go back to the changes without the `team.html` page.

> Below are the solution steps
1. Create a new `home.html` file, add some html changes and save them.
```
user#   touch index.html

user#   ls

>       index.html

user#   nano index.html     //make changes to the file

user#   cat index.html      //preview the file

 >      <html>
 >      <head><head>
 >      <body>
 >          <p>This is some text</p>
 >      </body>
 >      </html>
```

2. Stash save your current changes
```
user#   git stash push -m "first_stash"

>       Saved working directory and index state On dev: first_stash
```
3. Repeat the same process for a new `about.html` page and stash save your changes
4. Repeat the same process for a new `team.html` page and stash save your changes
```
user#   touch about.html

user#   nano about.html         //make changes to the about page

user#   cat about.html          //preview the about page

 >      <html>
 >      <head><head>
 >      <body>
 >          <p>This is the about Page </p>
 >      </body>
 >      </html>

user#   git stash push -u -m "second_stash"

>       Saved working directory and index state On dev: second_stash

user#   touch team.html

user#   nano team.html          //make changes to the team page

user#   cat team.html          //preview the team page

 >      <html>
 >      <head><head>
 >      <body>
 >          <p>This is the Team Page </p>
 >      </body>
 >      </html>

user#   git stash push -u -m "third_stash"

>       Saved working directory and index state On dev: third_stash
```
5. Using stash pop restore the changes of the `about.html` page
```
user#   git stash list         // list all the stashes

>       stash@{0}: On dev: third_stash
>       stash@{1}: On dev: second_stash
>       stash@{2}: On dev: first_stash

user#   git stash pop stash@{1}     //restore the stash with index in the {id}

>       Already up to date.
>       On branch dev
>       Your branch is up to date with 'origin/dev'.
>       Untracked files:
>         (use "git add <file>..." to include in what will be committed)
>       	about.html
>       	index.html
>       nothing added to commit but untracked files present (use "git add" to track)
>       Dropped stash@{1} (bd011daf7ca8a11e9790d723ebac0e354fcc8903)
```
6. With the help of an `index` use `stash pop` bring back the `home.html` page changes
```
user#   git stash list

>       stash@{0}: On dev: third_stash
>       stash@{1}: On dev: second_stash
>       stash@{2}: On dev: first_stash

user#   git stash pop stash@{2}
```
7. Commit the current changes and push them
```
user#   git add .

user#   git commit -m "restore home and about pages"

>       [dev 26188b7] restore home and about pages
>        2 files changed, 12 insertions(+)
>        create mode 100644 about.html
>        create mode 100644 index.html

user#   git push -u origin dev

>        Enumerating objects: 5, done.
>        Counting objects: 100% (5/5), done.
>        Delta compression using up to 8 threads
>        Compressing objects: 100% (4/4), done.
>        Writing objects: 100% (4/4), 471 bytes | 471.00 KiB/s, done.
>        Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
>        To github.com:gisachris/git_project_one.git
>           a512875..26188b7  dev -> dev
>        branch 'dev' set up to track 'origin/dev'.
```

8. Using stash pop restore the changes of the `team.html` page index.
```
user#   git stash list

>       stash@{0}: On dev: third_stash
>       stash@{1}: On dev: second_stash
>       stash@{2}: On dev: first_stash

user#   git stash pop stash@{0}
```

9. Reset the current changes using `git reset` and go back to the changes without the `team.html` page.
```
user#   git reset --hard HEAD~1
```
<br>

---


## Bundle Two
### Exercise One
> Below are the exercise Question criteria
1. Create a new branch named `ft/bundle-2`
2. Add new changes to your project. create a new page named `services.html` and add some changes
3. Commit your changes and create a Pull Request against the `main` branch in your github repository
4. Request a review and make sure your Pull request gets merged (Look for someone to merge your PR)

1. Create a new branch named `ft/bundle-2`
```
user#   git checkout -b ft/bundle-2

>       Switched to a new branch 'ft/bundle-2'
```
2. Add new changes to your project. create a new page named `services.html` and add some changes
```
touch services.html
user#       nano services.html          // make changes to the services.html page

user#       cat services.html           //preview the changes

>           <html>
>             <body>
>               <p>this is the services page</p>
>             </body>
>           </html>
```

3. Commit your changes and create a Pull Request against the `main` branch in your github repository
```
user#       git add .

user#       git commit -m "implement the services page"

>           [ft/bundle-2 3617987] implement the services page
>            1 file changed, 5 insertions(+)
>            create mode 100644 services.html

user#   git push -u origin ft/bundle-2

>       Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
>       remote: 
>       remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
>       remote:      https://github.com/gisachris/git_project_one/pull/new/ft/bundle-2
>       remote: 
>       To github.com:gisachris/git_project_one.git
>        * [new branch]      ft/bundle-2 -> ft/bundle-2
>       branch 'ft/bundle-2' set up to track 'origin/ft/bundle-2'.
```
4. Request a review and make sure your Pull request gets merged (Look for someone to merge your PR)

<img src='./images/bundle_two_exercise_one.png'>

<br>

---
### Exercise Two
> Below are the exercise Question criteria

<br>

---


