# DSCoP Class 7 Lab Notes

Welcome to the Data Science Community of Practice Class 7 Lab!

When you first join a project and need access to the code:
`git clone <url_of_repo>`

For information about what branch you are on and what you have changed:
`git status`

When you want to make sure the branch you are on is up to date:

`git pull`

or

`git fetch`

`git merge`

When you want to switch to a different branch (only allowed if all changes on the current branch are committed or stashed):

`git checkout <name_of_branch_to_switch_to>`

When you want to create a new branch off of the current branch (the resulting branch is local and will not be visible to your collaborators yet):

`git checkout -b <your_branch_name>`

Once you’ve modified the code in your new branch and want to push your branch to the remote repository for your collaborators to review, you:
Stage your branch:

`git add <file_you_changed_1> <file_you_changed_2>`

Commit your branch:

`git commit -m “Message saying what you did goes here.”`

Push your branch to the repository:

`git push`

if you haven’t ever pushed this branch before, it only exists locally, that is, it is only on your machine and doesn’t exist in the remote repo yet.  In that case, you will need to create the remote (or “upstream”) branch location as part of the push (git will prompt you if you forget this syntax):

`git push --set-upstream origin <your_branch_name> `

Now your branch is visible to your collaborators.  To merge it into master, you need to do the following steps:
* Create a pull request (PR) and identify a collaborator who will review your PR. 
* When your collaborator has finished reviewing your PR, she will either Approve or Request Changes.  If she has requested changes, you will make the necessary changes on your branch and then do the add+commit+push commands again to get them to the remote repository where she can see them.  Then she (or another collaborator) will need to review again.  Iterate until the PR is Approved.  
* Merge with master:

`git checkout master` (switch to the master branch)

`git merge <your_branch_name>` (merge your branch into master)

You may have merge conflicts if both you and another collaborator have modified the same section of code, and they merged their code to master before you.  In that case, one way to fix the merge conflicts is to:

`git checkout <your_branch_name> (switch to your branch)`

`git merge <your_branch_name> (merge master into your branch)`

The files that both of you edited will be marked with:

`<<<<<<< HEAD`

`the content that your collaborator wrote, which is currently in master`

`=========`

`the content that you wrote`

`>>>>>>>> your_branch_name`

Edit this to keep the content you want and delete the rest, including the <<<, ===, and >>> lines.  Do this for all the merge conflicts.  Then do another add+commit+push and request a PR review.

Excellent git e-book here: https://git-scm.com/book/en/v2
