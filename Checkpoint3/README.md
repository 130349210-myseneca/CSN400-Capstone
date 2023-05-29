# Checkpoint 3 Submission

- **COURSE INFORMATION: NDD**
- **STUDENT’S NAME: Kinod Lakdinu Melewa Thanthrige**
- **STUDENT'S NUMBER: 130349210**
- **GITHUB USER_ID: 130349210-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**

### Table of Contents
1. [Part A - Manage Conflicts - Overwrite Remote Changes](#header1)
2. [Part B - Manage Conflicts - Reset Local Commit Head](#header2)
3. [Part C - Manage Conflicts - Merge Editor](#header3)
4. [Part D - Collaboration - Creating Pull Request](#header4)

### **Part A - Manage Conflicts - Overwrite Remote Changes**
- **Part 1 - Conflict-error.log**

Pushing to https://github.com/130349210-myseneca/CSN400-Capstone.git
To https://github.com/130349210-myseneca/CSN400-Capstone.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/130349210-myseneca/CSN400-Capstone.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

- **Part 1 - Conflict-overwrite.log**

POST git-receive-pack (226518 bytes)
remote: Resolving deltas:   0% (0/33)        
remote: Resolving deltas:   3% (1/33)        
remote: Resolving deltas:   6% (2/33)        
remote: Resolving deltas:   9% (3/33)        
remote: Resolving deltas:  12% (4/33)        
remote: Resolving deltas:  15% (5/33)        
remote: Resolving deltas:  18% (6/33)        
remote: Resolving deltas:  21% (7/33)        
remote: Resolving deltas:  24% (8/33)        
remote: Resolving deltas:  27% (9/33)        
remote: Resolving deltas:  30% (10/33)        
remote: Resolving deltas:  33% (11/33)        
remote: Resolving deltas:  36% (12/33)        
remote: Resolving deltas:  39% (13/33)        
remote: Resolving deltas:  42% (14/33)        
remote: Resolving deltas:  45% (15/33)        
remote: Resolving deltas:  48% (16/33)        
remote: Resolving deltas:  51% (17/33)        
remote: Resolving deltas:  54% (18/33)        
remote: Resolving deltas:  57% (19/33)        
remote: Resolving deltas:  60% (20/33)        
remote: Resolving deltas:  63% (21/33)        
remote: Resolving deltas:  66% (22/33)        
remote: Resolving deltas:  69% (23/33)        
remote: Resolving deltas:  72% (24/33)        
remote: Resolving deltas:  75% (25/33)        
remote: Resolving deltas:  78% (26/33)        
remote: Resolving deltas:  81% (27/33)        
remote: Resolving deltas:  84% (28/33)        
remote: Resolving deltas:  87% (29/33)        
remote: Resolving deltas:  90% (30/33)        
remote: Resolving deltas:  93% (31/33)        
remote: Resolving deltas:  96% (32/33)        
remote: Resolving deltas: 100% (33/33)        
remote: Resolving deltas: 100% (33/33), done.        
Pushing to https://github.com/130349210-myseneca/CSN400-Capstone.git
To https://github.com/130349210-myseneca/CSN400-Capstone.git
 + 6e0a6ba...41deae5 main -> main (forced update)
updating local tracking ref 'refs/remotes/origin/main'


### **Part B - Manage Conflicts - Reset Local Commit Head**

- **Part 2 - Conflict-overwrite.log**

Pushing to https://github.com/130349210-myseneca/CSN400-Capstone.git
To https://github.com/130349210-myseneca/CSN400-Capstone.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/130349210-myseneca/CSN400-Capstone.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.


- **Part 2 - Pull-error.log**

error: Pulling is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.


- **Part 2 - Pull-success.log**

POST git-upload-pack (196 bytes)
From https://github.com/130349210-myseneca/CSN400-Capstone
 = [up to date]      main       -> origin/main
Auto-merging Checkpoint3/conflict-resolution/index.html
CONFLICT (content): Merge conflict in Checkpoint3/conflict-resolution/index.html
Automatic merge failed; fix conflicts and then commit the result.


- **Part 2 - Reset-head.log**

HEAD is now at b6b4e90 modifies style color in index.html to darkolivegreen
commit b6b4e90d309bfe4eeaf73e8e4bfdfdd5b384b69e
Author: Kinod <klmelewa-thanthrige@myseneca.ca>
Date:   Mon May 29 14:38:06 2023 -0400

    modifies style color in index.html to darkolivegreen


### **Part C - Manage Conflicts - Merge Editor**

- **Part 3 - Pull-conflict.log**

POST git-upload-pack (375 bytes)
POST git-upload-pack (968 bytes)
From https://github.com/130349210-myseneca/CSN400-Capstone
 
 * branch            feat-body-text -> FETCH_HEAD
 * [new branch]      feat-body-text -> origin/feat-body-text
Auto-merging Checkpoint3/conflict-resolution/index.html
CONFLICT (content): Merge conflict in Checkpoint3/conflict-resolution/index.html
Automatic merge failed; fix conflicts and then commit the result.

- **Part 3 - Status.log**

On branch main
Your branch is up to date with 'origin/main'.

All conflicts fixed but you are still merging.
   (use "git commit" to conclude merge)

Changes to be committed:
	modified:   Checkpoint3/conflict-resolution/index.html

- **Part 4 - Screenshot of Complete Merge**


### **Part D - Collaboration - Creating Pull Request**

- **Part 4 - Pull Request Summary Screenshot**



