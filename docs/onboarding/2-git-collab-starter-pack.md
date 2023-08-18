# Git Collab Starter Pack

This starter pack encompasses creating issues, developing on separate branches, initiating pull requests, and undergoing code reviews to facilitate organized and collaborative software development.

## Branch Protection

Enforcing branch protection on `main` branch enhances code stability and security by preventing accidental deletions and unauthorized direct pushes, ensuring that changes undergo proper code review and testing processes through pull requests.

## Creating/Choosing an Issue

Identify a task, bug, or enhancement, then either creating a new issue or selecting an existing one to track and discuss specific development objectives within a repository.

===  "Issue Template"

    ```md
    <TICKET_NAME-TICKET_NUMBER> <SCOPE> <TICKET_DESCRIPTION>

    - <TICKET_DETAILS>...
    ```

===  "Sample Issue"

    ```md
    Platformer-123 Gameplay Improvements

    - Ticket Details:
    Implement various gameplay enhancements to improve player experience.

    - Scope:
    Gameplay mechanics, player movement, enemy behavior, collision detection.

    - Expected Changes:
    - Improve player movement responsiveness.
    - Add double jump mechanic for better platforming.
    - Adjust enemy AI behavior for more engaging challenges.
    - Refactor collision detection to reduce glitches.
    ```

!!! note

    To mitigate merge conflicts, each issue will be assigned to a maximum of one developer in order to maintain clear ownership and minimize overlapping changes.

## Creating a new branch

Making a copy of the current state of a repository to work on separate changes without affecting the main codebase.

```bash
git checkout -b <branch_name>
```

### Branch Naming Convention

=== "With Ticket Number"

    ```bash
    <TICKET_TYPE>/<TICKET_NAME-TICKET_NUMBER>
    ```

=== "Example"

    ```bash
    feat/PLAYER-256
    docs/README-1
    ```

<span></span>

=== "With Ticket Description"

    ```bash
    <TICKET_TYPE>/<TICKET_DESCRIPTION>
    ```

=== "Example"

    ```
    bugfix/misconfigured-lint-workflow
    docs/add-locale-translations
    ```

## Working on the local branch

Make changes to files within the branch, separate from the main codebase, allowing for isolated development.

## Pushing from local to remote

Update the remote branch with your local changes, facilitating collaboration and sharing of development progress.

=== "Origin NOT SET"

    ```bash
    git push -u origin <branch_name>
    ```

=== "Origin already set"

    ```bash
    git push
    ```

## Creating a Pull Request

A pull request is a formalized way to propose and discuss changes made in a branch, enabling collaboration and code review before merging those changes into the main branch.

=== "PR Template"

    ```md
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

=== "Sample PR"

    ```md
    Platformer-123 Gameplay Improvements

    Ticket Link: [#123](https://example.com/tickets/123)
    Description: Implement various gameplay enhancements to improve player experience.

    Changes made:
    - Improved player movement responsiveness.
    - Added double jump mechanic for better platforming.
    - Adjusted enemy AI behavior for more engaging challenges.
    - Refactored collision detection to reduce glitches.

    Expected Behavior:
    - Players will experience smoother and more responsive character control.
    - The game's difficulty will be balanced due to the addition of double jump.
    - Enemies will present a more dynamic and engaging threat with AI adjustments.
    - Players will encounter fewer collision-related bugs and issues.

    Test Steps:
    1. Launch the game.
    2. Play through different levels using various characters.
    3. Attempt different platforming maneuvers, including double jumps.
    4. Observe enemy behavior changes in different scenarios.
    5. Pay attention to collision interactions with the environment.

    Before
    ![Before Changes](link_to_before_screenshot_or_gif)

    After
    ![After Changes](link_to_after_screenshot_or_gif)
    ```

### Code Review

Code review is a collaborative process where changes made in a branch are systematically evaluated by peers to ensure quality, identify errors, and provide feedback before merging.

### Pull Request Approval

If changes are approved, merge the PR, then and only then, will the changes reflect to the `main` branch

## Update changes from remote

Switch back to main and pull latest changes made by other devs.

```bash
git checkout main
git pull
```
