# Git Exercises - part 1

---

## 1. Initialise a new git repo:

1. Create a new folder inside `prep-steps` called `git-practice`. 
2. Navigate into this directory and run `ls -a`. What do the `.` and `..` refer to? - . (single dot) → refers to the current directory you are in.

.. (double dots) → refers to the parent directory (the folder one level above
. = /home/aaron-clifford/northcoders/prep-steps/git-practice

.. = /home/aaron-clifford/northcoders/prep-steps

3. To turn this directory into a git repository, run `git init`.
4. Run `ls -a` again to see the `.git` directory which means your repository has been successfully initialised. Done 
5. Confirm this has worked by running `git status`. It should output the name of the branch you are on with no commits yet and no changes at this point.

On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)


---

## 2. Make changes:

Git is now watching for changes made inside this directory.

1. Inside `git-practice` create a new file called `films.txt` and add a film title here.
2. Run `git status` to see that this change you've made is currently untracked by git.

aaron-clifford@aaron-clifford-HP-Spectre-x360-Convertible-15-ch0xx:~/northcoders/prep-steps/git-practice$ echo 'Dune' > flims.txt
aaron-clifford@aaron-clifford-HP-Spectre-x360-Convertible-15-ch0xx:~/northcoders/prep-steps/git-practice$ ls
flims.txt
aaron-clifford@aaron-clifford-HP-Spectre-x360-Convertible-15-ch0xx:~/northcoders/prep-steps/git-practice$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	flims.txt

nothing added to commit but untracked files present (use "git add" to track)
aaron-clifford@aaron-clifford-HP-Spectre-x360-Convertible-15-ch0xx:~/northcoders/prep-steps/git-practice$ 



## 3. Commit your changes:

Now that we have changes to our files, we can save those changes to our branch. This is called a `commit`.

1. Add the file you've created to git's staging area.

$ git add flims.txt

2. Once you've added the file, run `git status` again to confirm that this file is now in the staging area.
n branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   flims.txt


3. Now the file is added, commit the changes. Make sure you write an informative message about the change being made.

$ git commit -m 'favourite film'

[master (root-commit) 2dbf0c3] favourite film
 1 file changed, 1 insertion(+)
 create mode 100644 flims.txt


4. To confirm the commit has been made successfully, run `git log` to view the history. Press `Q` to exit the log.

$ git log 

commit 2dbf0c32ee8c8499b391e70659e6dddf197e1e2f (HEAD -> master)
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 10:52:17 2025 +0100

    favourite film


---

## 4. Further changes:

We can continue to work on the repo and commit changes at appropriate points.

1. Add another film to the `films.txt` file, then repeat the steps from before to commit that change.

echo 'Drive' >> flims.txt

2. Confirm that these changes have been successful with `git status` and `git log`.

Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 11:00:18 2025 +0100

    film added back

commit 8dcb6b6657c5559fc51fe2e61894ef0df2a00d73
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 10:57:12 2025 +0100

    adding a ryan gosling classic

commit 2dbf0c32ee8c8499b391e70659e6dddf197e1e2f
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 10:52:17 2025 +0100

    favourite film

---

## 5. Multiple changes:

Most real world work will involve making changes to more than one file. When making commits, we can be selective about which changes are staged and committed.

1. Add a final film to `films.txt`.
2. Create another file called `snacks.txt` and add your favourite film night snacks to it.
3. As the above changes are unrelated, make two separate commits for these changes. Remember, you will need to add and commit the files individually.

done 
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 11:13:13 2025 +0100

    Mate I like them okay

commit af53b7a991229d3784d44ee76e3d9f29efeee756
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 11:11:34 2025 +0100

    Toby M Classic

commit e62b1e295c952deb1a447f22972bec6abec63431
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 11:00:18 2025 +0100

    film added back

commit 8dcb6b6657c5559fc51fe2e61894ef0df2a00d73
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 10:57:12 2025 +0100

    adding a ryan gosling classic

commit 2dbf0c32ee8c8499b391e70659e6dddf197e1e2f
Author: ACLIFF123 <aaronclifford26@gmail.com>
Date:   Thu Sep 18 10:52:17 2025 +0100

    favourite film



**Tip:** There are lots of conventions for writing commit messages. We will follow a standard practice of writing commits in the present tense that describe the change they make, e.g. "fix bug" rather than "fixed bug".

This matches the style git itself uses in auto-generated messages and forms a timeline.

Imagine you are coming back to work on this project in 6 months time. The commit message should tell you what's happening at any point in time.

If you're struggling to describe your changes, a good rule of thumb is to complete the sentence:

This commit will "commit message here"

---
