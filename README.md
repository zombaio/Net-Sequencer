Net-Sequencer
=============

A loop based sequencer designed to control MIDI receiving software connected over a network.  It will be either desktop or iOS/Android, probably using the NetJACK network audio/midi connection kit.

## Git

### Tutorials

A particularly nice one:

  http://pcottle.github.io/learnGitBranching/

A load more:

  https://www.bento.io/git

The official book:

  http://git-scm.com/book

### Our Method

To pull from to the remote master branch:

    git pull --rebase origin master

That will fast forward your local commits on the master branch past the commits from the remote that were just downloaded.

To pull from another remote branch:

  same as above but replace _master_ with _branch name_

To push local commits to the remote master branch:

_first,_

    git pull --rebase origin master

_then after sorting out conflicts,_

  *Check the program still builds and works locally.*

_finally,_

    git push origin master

*Note*: omitting the --rebase keyword will run an automatic merge, which is usually unwanted.

When implementing a new feature/bug fix independently (i.e. anything you wish to work independently on and only involves one remote branch):

- When finally pushing to the remote, please use the above method. 

When implementing a new feature as a team:

- Create a new side branch on the remote to work on.  When the feature is complete/readyish it can be _merged_ into the master branch.
Its also a good idea to merge the master branch into the side branch occasionally so that merging back into the master branch runs a bit smoother.

*Summary*
- Rebase when pulling to update a local branch.
- Check a local build before pushing.
- Never merge branches such that what you push onto a single remote branch will have a non-linear history, unless it concerns already existing  branches on the remote that need merging.
- Revert already pushed changes rather than resetting them
