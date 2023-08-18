# Git Starter Pack

This starter pack covers fundamental commands for version control.
## Cloning a Repo

Create a copy of a remote repository onto your local machine.

```bash
git clone <repo_name>
```

## Adding changes

Add modified files to the staging area and prepare them for a commit.

### Adding selected files/directories

Stage only chosen modifications for the next commit.

```bash
git add <file_1> <file_2> <dir_1> ...
```

### Adding all changes made

Stage all modifications across the entire working directory for the upcoming commit.

```bash
git add .
```

## Committing the changes made

Create a snapshot of the staged changes along with a descriptive message, recording a new point in the project's history.

```bash
git commit -m "<message>"
```

### Descriptive commit message

A descriptive commit message provides clear context and history, aiding collaboration and future reference for understanding the purpose and impact of the committed changes.

```bash
feat: <message>          # adding/deleting feature changes
bugfix: <message>        # fixing bugs
chore: <message>         # any changes not feat/bugfix
docs: <message>          # improve documentation
```

## Push changes from local to remote

Transmit your local commits and changes to a shared repository, enabling collaboration and synchronization with other team members.

```bash
git push
```

## Pull changes from remote to local

Fetch and integrate the latest updates from the shared repository into your local codebase.

```bash
git pull
```
