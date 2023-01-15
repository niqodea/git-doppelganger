# Git Doppelganger

Git Doppelganger combines the advantages of `git rebase` and `git merge` to provide a seamless way to clean up your Git history while still preserving it.

With Git Doppelganger, you can work on a "doppelganger" branch that is a copy of your original branch in terms of the files, but not in terms of the history.
This means you can freely rebase on the doppelganger branch to clean up your Git history, without affecting the history of the original branch.

The magic behind Git Doppelganger is in its use of Git hooks, which automatically sync your work on the doppelganger branch back to the original branch whenever you commit.
This ensures that the original branch is kept up to date with the doppelganger branch, while preserving its history.
And because the state of the repository in both branches is always the same (i.e., the files are exactly identical), you won't have to worry about lost work.

Git Doppelganger is a useful tool for anyone looking to clean up their Git history without sacrificing the important information that history provides.
Give it a try and see how it can help improve your workflow!

## Installation

To install Git Doppelganger, you will need to clone the repository and run the install script to install it on your machine.

```sh
git clone git@github.com:niqodea/doppelganger.git
doppelganger/install
```

Once installed, you will have access to a new class of doppelganger commands, prefixed with `git dpg`.

## Using Git Doppelganger

### Setting up a Repository

To set up an existing Git repository to use Doppelganger, you can run the following command:

```sh
git dpg install-hooks
```

This will install the necessary hooks in the repository to use Doppelganger.

### Creating a Doppelganger Branch

To create a doppelganger branch, you can run the following command:

```sh
git dpg init
```

This command will create a doppelganger branch for the current branch you are working on.
You can now work on the doppelganger branch without worrying about overwriting the history.
All the history will be preserved in the original branch.

### Synchronizing the Original Branch

When updating your doppelganger branch, you will sometimes be prompted to provide a commit message for the original branch to keep it in sync.
This typically happens when amending a commit or after a git rebase, since an appropriate commit message cannot be automatically retrieved from the doppelganger history in those cases.
You will be provided with the diff introduced by the commit so that you can come up with a meaningful message for it.

### Closing a Doppelganger Branch

Once you have finished working on your doppelganger branch, you may want to retain either the doppelganger history, the original history, or both.
Git Doppelganger provides three different modes to handle the closing of the doppelganger branch: `keep-original`, `keep-doppelganger`, and `merge`.

#### `keep-original`
This mode will retain the original history and discard the doppelganger.
The original branch will be unchanged and the doppelganger branch will be deleted.
This mode can be used when you want to discard the changes made in the doppelganger branch and keep the original history intact.

```sh
git dpg close -m keep-original
```

#### `keep-doppelganger`
This mode will retain the doppelganger history and discard the original.
The original branch will be made to point to the doppelganger history, and the doppelganger branch will be deleted.
This mode can be used when you want to keep the changes made in the doppelganger branch and discard the original history.

```sh
git dpg close -m keep-doppelganger
```

#### `merge`
This mode will merge the clean history of the doppelganger branch into the original branch, preserving both the original and doppelganger history.
The doppelganger branch will be deleted, and the original branch will be updated with the clean history of the doppelganger.
This mode can be used when you want to retain both the original and doppelganger history and merge them together.

```sh
git dpg close -m merge
```

