!SLIDE bullets incremental

# General Workflow #

* Clone an svn branch
* Stage modifications
* Commit changes (local)
* Update from svn
* Push to svn

!SLIDE commandline incremental

# Introduce yourself #

    $ git config --global user.name "Blair Kitchen"

    $ git config --global user.email "blair.kitchen@cobham.com"

!SLIDE commandline incremental

# Clone an svn branch #

    $ git svn clone http://svn/git-svn/trunk git_repo
    Initialized empty Git repository in git_repo/.git/
    r1 = e1e2a18c6537614f2bebc5c0dfb4ac6f8c829a3b (git-svn)
        A   file1.c
        A   Makefile
    r2 = 58e044c16678b0a8b92e4dbed8f0a69d48ba9ec1 (git-svn)
    Checked out HEAD:
      file:///Users/blair/git-svn/SVNROOT/trunk r2

!SLIDE bullets incremental

# What did we just do? #

* Created a local copy of svn branch
* All revisions downloaded from server
* Done _once_ per branch
* Only necessary at beginning of sprint

!SLIDE bullets incremental

# Staging Modifications #

* Changes placed in index _before_ committing
* svn has no concept of an index
* Break changes into multiple commits
* Build commit from the ground up

!SLIDE commandline incremental

# git add #

    $ git add platform.h

    $ git add --patch platform.h

!SLIDE bullets incremental

# Viewing Status #

* Use 'git status' to see local changes
* Shows changes placed in index
* Shows unstaged changes
* Identical in purpose to 'svn status'

!SLIDE commandline incremental

# git status #

    $ git status

!SLIDE bullets incremental

# Commit Changes #

* Commit moves index into formal history
* Commit identified by SHA1 hash (not rev number)
* Associate a log message

!SLIDE commandline incremental

# git commit #

    $ git commit

    $ git commit --amend

!SLIDE bullets incremental

# Update from svn #

* Uses a rebase operation
* Local changes rolled back
* Changes from svn applied
* Local changes applied
* Conflicts resolved on a per-commit basis

!SLIDE commandline incremental

# git svn rebase #

    $ git svn rebase
        M   Makefile
    r3 = ae409c2f5fe0831f22d6dc891652b5f9159f35de (git-svn)
    First, rewinding head to replay your work on top of it...
    Applying: Local git commit.

!SLIDE bullets incremental

# Push to svn #

* Once ready, changes are pushed to svn
* No going back
* Each local commit appears in svn
* Be sure only desired changes are in history

!SLIDE commandline incremental

# git svn dcommit #

    $ git svn dcommit
    Committing to http://svn/git-svn/trunk ...
        M   file1.c
    Committed r4
        M   file1.c
    r4 = 31a4b40b05e1b42f34dd22c34936f43dd5be90ec (git-svn)
    No changes between current HEAD and refs/remotes/git-svn
    Resetting to the latest refs/remotes/git-svn
