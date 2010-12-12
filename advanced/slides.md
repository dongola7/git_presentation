!SLIDE bullets incremental

# Advanced Topics #

* Reverting changes
* Branching and merging

!SLIDE bullets incremental

# Reverting Changes #

* Performed via 'checkout' command
* Restores named file to index, _not_ last commit
* Use 'reset' to remove changes from index

!SLIDE commandline incremental

# Reverting Changes #

    $ git checkout platform.h

    $ git reset platform.h

    $ git reset --hard HEAD


!SLIDE bullets incremental

# Branching and Merging #

* Two commands: 'branch' and 'merge'
* Git supports non-linear history
* trunk = master
* Perform most work on a branch

!SLIDE commandline incremental

# Creating a branch #

    $ git branch
    * master
    $ git checkout -b my_branch
    Switched to a new branch 'my_branch'
    $ git branch
      master
    * my_branch

!SLIDE bullets incremental

# Merging Changes #

* Git supports non-linear history, SVN does not
* Keep linear history in your repository
* Use 'rebase' to prevent this

!SLIDE commandline incremental

# Merging Changes #

    $ git rebase master
    Current branch 'my_branch' is up to date.
    $ git checkout master
    Switched to branch 'master'
    $ git merge temp
    Updating fd6711a..3fc6258
    Fast-forward
     tests.tcl |   70 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
     1 files changed, 70 insertions(+), 0 deletions(-)

!SLIDE bullets incremental

# Best Practices #

* Maintain linear history.  Do not dcommit merge commits
* Do not amend, reorder, or change commits in SVN
* Maintain 'master' branch as integration branch
* Perform work on feature branches, merging as necessary

!SLIDE bullets

# Further Reading #

* http://gitref.org
* http://git-scm.com
