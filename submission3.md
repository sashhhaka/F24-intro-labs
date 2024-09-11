## Task 1: Understanding Version Control Systems

Git objects:
- Blob: Stores file data.
- Tree: Stores the directory structure and file mappings.
- Commit: Points to a tree and stores metadata like author, committer, commit message, and parent commit(s).

---

### Tree
Here is a corresponding tree object for the lab3 branch:
```bash
git cat-file -p 'lab3^{tree}'
```
Output:
```
100644 blob ede183da8ef201e5f5737eea502edc77fd8a9bdc    README.md
100644 blob 5738bc15a0416ad2624df13badfb235052777e79    index.html
100644 blob 7a94f7af59b8968be392288ea03179a24ffc9d9e    lab1.md
100644 blob 1b99cc0044f93f556a0f6a599c7edf2f33f4944a    lab2.md
100644 blob 2f8463cc188ec6ca69ae7a0f98d38e132280becb    lab3.md
100644 blob d66a6867f90e48f6f44d9d80821aa1d866a24882    lab4.md
100644 blob b963fefec8154de7f4279f1b0615893b4911a4c4    submission3.md
```
---

### Blob
Now, let's inspect the contents of the `submission3.md` file:
```bash
git cat-file -p b963fefec8154de7f4279f1b0615893b4911a4c4
```
Output:
```markdown
Test commit
```
--- 
### Commit
Finally, let's look at the commit object for the latest commit:
Let's find the latest commit hash:
```bash
git rev-parse HEAD
```
Output:
```
cbf22a0dcb52c517b2646e29d0741f91a7a8587d
```

Now, let's inspect the contents of the commit object:
```bash
git cat-file -p cbf22a0dcb52c517b2646e29d0741f91a7a8587d
```

Output:
```
tree d667eaa3e0861294db85a3103eb2c46d04fa189f
parent 30433d0d4de51989a5bd0932349b954e673ae719
author Alexandra Vabnits <aleksandra.vabnits@lemanapro.ru> 1726074614 +0300
committer Alexandra Vabnits <aleksandra.vabnits@lemanapro.ru> 1726074614 +0300
gpgsig -----BEGIN SSH SIGNATURE-----
 U1NIU0lHAAAAAQAAADMAAAALc3NoLWVkMjU1MTkAAAAgyDvWOd8ssgvHZk3h6jXmYizaWn
 3rAvK4PO85ym1KMkIAAAADZ2l0AAAAAAAAAAZzaGE1MTIAAABTAAAAC3NzaC1lZDI1NTE5
 AAAAQKytlcKOghoyjRGxitXP+9lZZHVpLJwU12aEfpb22IOVftdByY50DstbT2dl54MdF/
 tKuH9hQUPdtRV3gmIAIwA=
 -----END SSH SIGNATURE-----

test commit
```
Alternatively, we can use the following command to view the last commit object:
```bash
git cat-file -p HEAD
```

Now, we can also use the hash of tree object to see the contents of the tree object:
```bash
git cat-file -p d667eaa3e0861294db85a3103eb2c46d04fa189f
```
Output:
```
100644 blob ede183da8ef201e5f5737eea502edc77fd8a9bdc    README.md
100644 blob 5738bc15a0416ad2624df13badfb235052777e79    index.html
100644 blob 7a94f7af59b8968be392288ea03179a24ffc9d9e    lab1.md
100644 blob 1b99cc0044f93f556a0f6a599c7edf2f33f4944a    lab2.md
100644 blob 2f8463cc188ec6ca69ae7a0f98d38e132280becb    lab3.md
100644 blob d66a6867f90e48f6f44d9d80821aa1d866a24882    lab4.md
100644 blob b963fefec8154de7f4279f1b0615893b4911a4c4    submission3.md
```

## Task 2: Practice with Git Reset Command
I have experienced a beautiful moment of forgetting to commit the submission3.md, 
while executing hard reset in the this task, so almost written report needs to be rewritten again.
I guess, practice gives the best knowledge).

New branch was created:
```bash
git checkout -b git-reset-practice
```
Output:
```
Switched to a new branch 'git-reset-practice'
```

A series of commits was created:
```
[git-reset-practice a7b84b9] First commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file.txt

[git-reset-practice 4dfcc78] Second commit
 1 file changed, 0 insertions(+), 0 deletions(-)

[git-reset-practice 46a3c7d] Third commit
 1 file changed, 0 insertions(+), 0 deletions(-)
```

So, currently, git status does not show any changes in file.txt.

Now, try soft reset:
```bash
git reset --soft HEAD~1
git status
```
Output:
```
On branch git-reset-practice
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   file.txt
```
And the content of file.txt did not changed:
```
First commit
Second commit
Third commit
```

Basically, the last 'git commit' command was undone, but the changes are still in the working directory and the index.
To restore the changes we can simply commit them again:
```bash
git commit -m "Third commit"
```
Output:
```
[git-reset-practice 4bf3718] Third commit
 1 file changed, 0 insertions(+), 0 deletions(-)
```
git status again shows no changes.

Now, let's try hard reset:
```bash
git reset --hard HEAD~1
git status
```
