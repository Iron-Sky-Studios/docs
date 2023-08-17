# Git Collab Starter Pack

1. `main` branch is protected

    - cannot be deleted

    - cannot be directly pushed

2. To request for changes to main, create an `issue`/choose an existing `issue`

    - sample issue template

        ```bash
        <TICKET_NAME-TICKET_NUMBER> <SCOPE> <TICKET_DESCRIPTION>

        - <TICKET_DETAILS>...

        eg.
        [PLAYER-256] [Player 2] Add player 2 option

        - Add PvP (Player 1 vs 2)

        - Add CoOp (Players vs Environment)

            * Explore endless mode (low prio)
        ```

3. to avoid merge conflicts, tickets (`issues`) will be assigned to at most 1 dev

4. to start collabing, don't clone the repo, instead fork it and then clone the fork

5. since `main` is protected, create a new branch

    ```bash
    git checkout -b <branch_name>
    ```

    - branch naming convention

        ```bash
        <TICKET_TYPE>/<TICKET_NAME-TICKET_NUMBER>

        eg.
        feat/PLAYER-256
        docs/README-1

        -- can also be
        <TICKET_TYPE>/<TICKET_DESCRIPTION>

        eg.
        bugfix/misconfigured-lint-workflow
        ```

6. add changes and test your code in your local machine, before staging then committing

7. push local branch to remote

    - if upstream branch not set

        ```bash
        git push -u origin <branch_name>
        ```

    - if upstream is set

        ```bash
        git push
        ```

8. submit a `pull request`

    - sample PR template

        ```bash
        <TICKET_NAME-TICKET_NUMBER> <SCOPE> <TICKET_DESCRIPTION>

        Ticket Link: <link_to_ticket>
        Description: <verbose_description>

        Changes made:
        - <changelog_1>
        - <changelog_2>
        - ...

        Expected Behaviour:
        - expected behaviour after adding changes

        Test steps:
        - detail the steps to do to achieve or replicate expected behaviour
        from another dev's or collaborator's machine

        (Optional)
        Before
        <screenshot_or_gif_before_the_change>

        After
        <screenshot_or_gif_after_the_change>
        ```

9. other devs will review the code. they can either accept, reject, or request to revise. this step ensures code quality and also help catch stuff you might've missed

10. if changes are approved, then merge the PR. then and only then, will the changes reflect to the `main` branch

11. switch back to main and pull latest changes made by other devs

    ```bash
    git checkout main
    git pull
    ```

12. rinse and repeat
