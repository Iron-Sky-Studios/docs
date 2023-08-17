# Git Starter Pack


1. Cloning a Repo

    ```bash
    git clone <repo_name>
    ```

2. Add changes

    - Multiple files/directories

        ```bash
        git add <file_1> <file_2> <dir_1> ...
        ```

    - All changes in files/directories

        ```bash
        git add .
        ```

3. Commit the changes made

    ```bash
    git commit -m "<message>"
    ```

    - Best practices for more descriptive commit message

        ```bash
        feat: <message>          # adding/deleting feature changes
        bugfix: <message>        # fixing bugs
        chore: <message>         # any changes not feat/bugfix
        docs: <message>          # improve documentation
        ```

4. Push changes from local to remote

    ```bash
    git push
    ```

5. Pull changes from remote to local

    ```bash
    git pull
    ```
