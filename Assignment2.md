1.	Describe what is the output of the following commands

- Use `git branch` to list the branches in current repository.
- Use `git checkout` to switch the branches.
- Use `git log --decorate` to explore the structure of commits.

```
> cd ./handson
```
```
> git branch
*master
 math

> git checkout math
Switched to branch 'math'

> git log --decorate
commit e3c629dd524712aedea96d7dbaad1c50d12b5b5e (HEAD -> math)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:13:48 2019 -0700

    Adding some more knowledge to the function

commit 654b490a181dedf82dd6deda5f9848d6cca05918
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:12:14 2019 -0700

    Added a draft of A.py

commit 2dfb02c3f9383d6c3b2695c99e175d8b85f594a1
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:08:47 2019 -0700

     Creating all files (all empty)
```

2.	Try git log --graph --all. What do you see?
```
The tree with changes.

* commit 18931d12a8be7cac049b73c6bc8136e9482f3371 (master)
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Wed Aug 14 23:15:28 2019 -0700
| 
|     Making a small change here
|   
| * commit e3c629dd524712aedea96d7dbaad1c50d12b5b5e (HEAD -> math)
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Wed Aug 14 23:13:48 2019 -0700
|   
|       Adding some more knowledge to the function
| 
* commit 654b490a181dedf82dd6deda5f9848d6cca05918
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Wed Aug 14 23:12:14 2019 -0700
| 
|     Added a draft of A.py
| 
* commit 2dfb02c3f9383d6c3b2695c99e175d8b85f594a1
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Wed Aug 14 23:08:47 2019 -0700
```

3. Use git diff BRANCH_NAME to view the differences from a branch and the current branch. Summarize the difference from master to the other branch.

```
> git diff math master

diff --git a/A.py b/A.py
index 0afa98c..dc1e9bd 100644
--- a/A.py
+++ b/A.py
@@ -1,11 +1,3 @@
 #this is just an example, do not freak out
 def calculate_this(operator, num1, num2):
-   if operator == 'sum':
-      print num1 + num2
-      print 'That was easy buddy'
-   else:
-      if operator == 'subtraction':
-         print num1 - num2
-         print 'I could handle that...'
-      else:
-         print 'my knowledge is limited'
+   print 'my knowledge is limited'     
diff --git a/B.py b/B.py
index e69de29..c63f94c 100644
--- a/B.py
+++ b/B.py
@@ -0,0 +1 @@
+# Another file that will receive a line of code... at least.

```
Above is the detailed differences between the two branches, more generally, there are 2 files changed, 2 insertions(+), and 9 deletions(-)

4. Write a command sequence to merge the non-master branch into `master`

```
> git checkout master
> git merge handson

```


5. Write a command (or sequence) to (i) create a new branch called `math` (from the `master`) 
and (ii) change to this branch

```
> git checkout master
> git branch math
> git checkout math

```

6. Edit B.py adding the following source code below the content you have there
```
edit
print 'I know math, look:'
print 2+2
```

7. Write a command (or sequence) to commit your changes
```
> git add B.py
> git commit -m "add two lines in B.py on math branch"
```

8. Change back to the `master` branch and change B.py adding the following source code (commit your change to `master`):
```
edit
> print 'hello world!'
> git checkout master
> git add B.py
> git commit -m "add one lines in B.py on master branch"
```

9. Write a command sequence to merge the `math` branch into `master` and describe what happened
```
> git checkout master
> git merge math
```

10. Write a set of commands to abort the merge
```
> git merge --abort
```

11.	Now repeat item 9, but proceed with the manual merge (Editing B.py). All implemented functions are needed. Explain your procedure
```
No files copied

Auto-merging B.py
CONFLICT (content): Merge conflict in B.py
Automatic merge failed; fix conflicts and then commit the result.
```

12. Write a command (or set of commands) to proceed with the merge and make `master` branch up-to-date
```
> git checkout master
> git merge math
> git rebase

```

## comments:
```
Part 1.
- Open git console in default working directory
- Use `git branch` - `git checkout` - `git log --decorate` to see the current repo status
- Use `git log --graph --all` to see historical changes
- Create a branch using `git branch math`, but the math is already exit in the download file.
- Use `git diff math master` to see differences between these two banches.
- Back to master branch and use `git merge handson` to merge *math to *master.  
- Add the lines on B.py. Use `git add B.py` and `git commit -m "Add two lines in B.py on handson branch" to comment.
- Repeat the last step and add another line.
- Use `git merge --abort` to abort the previous merge.
- Use `git checkout master` - `git merge handson` - `git rebase` to get a up-to-date master branche.

I'm not familiar with the code and the location, so it is a hard process at hte beginning. The biggest problem is merging branches and conflicts are following.
```
