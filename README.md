# Git Doppelganger

Git Doppelganger is here to make your development life easier by merging the benefits of `git merge` and `git rebase`, allowing you to refine your Git history without losing any critical information.
With Git Doppelganger you create a "doppelganger" branch, a reflection of your original branch in file structure but not in history.
This allows you to make modifications and rebase freely without touching the original branch's history.

Magic? No, it's our use of Git hooks! They sync your doppelganger branch back to the original one with every commit, ensuring no loss of work and keeping histories intact.


## Quick Start

### Installation

Clone and run the install script:

```sh
git clone git@github.com:niqodea/doppelganger.git
doppelganger/install
```

Post-installation, use the `git dpg` prefixed commands.

### Setup & Usage

#### Setup Repository with Doppelganger

```sh
git dpg install-hooks
```

#### Create a Doppelganger Branch

```sh
git dpg init
```

#### Synchronize Original Branch

You might need to manually input commit messages occasionally, especially after amending a commit or a rebase, to keep the original branch in sync.

#### Close a Doppelganger Branch

Decide the fate of your histories while closing the doppelganger branch. Here are your options:
- **Keep original:**  
   ```sh
   git dpg close -m keep-original
   ```
- **Keep doppelganger:**  
   ```sh
   git dpg close -m keep-doppelganger
   ```
- **Merge the two:**  
   ```sh
   git dpg close -m merge
   ```
