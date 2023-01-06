# Git Doppelganger
Git Doppelganger is a new program that combines the advantages of `git rebase` and `git merge` to provide a seamless way to clean up your Git history while still preserving it.

With Git Doppelganger, you can work on a "doppelganger" branch that is a copy of your original branch in terms of the files, but not in terms of the history.
This means you can freely rebase on the doppelganger branch to clean up your Git history, without affecting the history of the original branch.

The magic behind Git Doppelganger is in its use of Git hooks, which automatically sync your work on the doppelganger branch back to the original branch whenever you commit.
This ensures that the original branch is kept up to date with the doppelganger branch, while preserving its history.
And because the state of the repository in both branches is always the same (i.e., the files are exactly identical), you won't have to worry about lost work.

In summary, Git Doppelganger is a powerful tool for anyone looking to clean up their Git history without sacrificing the important information that history provides.
Give it a try and see how it can help improve your workflow!

