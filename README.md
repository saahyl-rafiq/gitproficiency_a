Git Proficiency Examination
===========================

how to take this test
---------------------

1. Follow the directions contained in this Readme
2. You should create output repos under your own Github repo so that graders of this examination can check your work
3. You should not alter anything in these Github repos


The Test
--------

### Section 1 Dealing with the origin (in this case, Github)

(if I ask you to commit changes, feel free to use whatever commit message you choose)

1. fork the following repos into your own github account
	* gitproficiency_a, gitproficiency_b, gitproficiency_c, gitproficiency_d
	* from git@github.com:kleetus

	discussion: this tests the ability to fork a github repo

2.  clone the above repos to your local drive

	discussion: this tests the ability to clone a githib repo

3. open the text file labeled "first_file.txt" contained within gitproficiency_a
	* change all occurrences of the word "shall" with "must"
	* commit this change back
	* push this commit to your forked repo of gitproficiency_a

	discussion: this tests the ability to perform a commit and a push to another external repo.

4. send a pull request to github name "kleetus" for gitproficiency_a for your fork

	discussion: this tests the ability to perform a pull request for repos that you may not have write ability to. 


5. create a new branch locally and also remote at the origin
	* create a remote branch called "test_branch" using only one call to git-checkout
	* make a small commit (alter anything) and push the new remote branch
	* run the git command to view all the branches both remote and local

	discussion: this tests the ability to create a remote branch locally and also remotely


6. Resetting a branch to be exactly like the HEAD of the same branch in origin
	* use git-reset and possibly some options with that command to make your branch have no differences with origin/master
	* you may need to use git-clean for convenience as well to remove any stray untracked files.

	discussion: this tests the ability to reset a code base to be inline with a remote branch. It also shows how to clean up your directories of files that may be unneeded and not rely on manual deletion



7. Pull changes from origin without use git-pull
	* Revert your branch to HEAD-1, effectively making your local branch one commit behind the origin
	* Without using git-pull, download a patch from origin for your branch. Hint: there is a git command for this.
	* Using yet another git command, apply the patch that you just received from the last step to the code base.

	discussion: this tests the ability to separate the git-pull command and use each of its parts separately



### Section 2 Dealing with a local repo

1. create a submodule in your local gitproficiency_a project using gitproficiency_b project.
	* push your changes into your forked repo for gitproficiency_a

	discussion: this tests the ability to create a submodule in a project.

2. alter the following file in the submodule gitproficiency_b: first_file.txt
	* change the first occurrence of "1776" to "1976", 
	* change directories to your top level of gitproficiency_a and do a git status. You should see a change for git_proficiency_b, the new sha should say "-dirty"
	* go back to the git_proficiency_b module, commit and push those changes
	* go back to the top level of gitproficiency_a and do a git status. You should see a change outstanding for git_proficiency_a, the changes should show "(new commits)"
	* add the changes for the gitproficiency_b project to the gitproficiency_a project. Commit and push the changes for this as well.

	discussion: this tests the ability to change a submodule. It also shows what the changes look like to the submodule's main project, both at unstaged changes level and when the changes are committed in the submodule. It shows the relationship between the main project and its submodule.	


3. alter the following file in gitproficiency_a: first_file.txt
	* change all occurrences of the word "must" with "shall" (reversing what you did for number 3)
	* commit the change
	* visit this url in a browser, http://71.19.146.178/push_changes_to_gitproficiency_a
	* perform a rebase against the original repo, git@github.com:kleetus/gitproficiency_a master branch
	* fix the impending merge conflicts that will occur, in all cases choose the REMOTE side, in other words choose the incoming changes and not your own changes
	* continue with the rebase and push the changes with the merge conflicts worked out

	discussion: this tests the ability to perform a rebase against a repo that is not "origin". It also tests if you can resolve a simple merge conflict and continue with a rebase operation

4. check what the differences are between one branch and another
	* find all the commits that exist in your new remote branch, but do NOT exist in the master branch
	* generate a patch (diff) of the lines that are different between the master branch and your new remote branch. Just alter one file to make this easier.

	discussion: this tests the ability to see what commits are different between branches and also tests the ability to generate a patch file. Also, it shows what the diff looks like.

5. Applying a patch file to a code base.
	* apply the patch file to the master branch
	* check git status
	* review your changes and stage them
	* commit but do not push the changes to the master branch's origin

	discussion: this tests the ability to apply a patch to a code base and then be able to stage and commit the changes

6. Amending a commit
	* make a change in the code base and commit the change (do not push).
	* make another small change some place else in the code.
	* amend the first commit that you just made (do not create 2 commits).
	* push the single commit to origin/master

	discussion: this tests the ability to amend a commit. 

7. Recovering a commit that seems lost
	* find the sha of the first commit made in gitproficiency_a using git-log
	* checkout this sha
	* stash any changes to the project after checking out this sha
	* make a small change and commit
	* issue the command: git checkout master
	* find the commit you just made on the last branch without switching branches
	* cherry-pick the commit into the master branch, resolve any merge conflict and push the commit into master branch origin

	discussion: this tests the ability to checkout a sha (not a formal branch). It also tests the ability to stash changes. It also tests the ability to cherry-pick a commit using git's reference log feature.

8. Tagging a sha
	* Apply the following annotated tag to the master branch: test_tag
	* use this test as part of the tag's message: "this is a test tag"
	* push the tag to origin

	discussion: this tests the ability to apply an annotated tag to a sha

9. Finding out what sha goes with which tag
	* Fetch all the tags for gitproficiency_a
	* using the latest tag, use a single git command to find out which sha this tag points to

	discussion: this tests the ability use git to find annotated tag references

10. Interactive rebasing
	* create a new local branch and checkout it out
	* make 3 small commits to this branch
	* perform a rebase against the master branch and use the interactive option for rebase
	* roll the 3 commits into one commit, but retain all the commit messages for each commit in the single commit
	* rebase the master branch against your new test branch
	* push that commit to origin






