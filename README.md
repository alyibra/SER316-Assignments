# Number Guessing Game

## Project Overview

A number guessing game in Java to practice git branching, merging, rebasing, squashing, cherry picking and resolving merge conflicts. The project is built and tested with Gradle.

## Branch Structure

- main: The stable branch with the original game and cherry-picked random-number hotfix.
- dev: This is the integration branch with the completed gameplay features and hotfix.
- feature1: Quitting, playing again, guess feedback improvements and version comment. This branch was merged into `dev` and deleted.
- feature2: Introduced up to 10 attempts, info about remaining attempts and game over.
- feature3: Introduced a hint system to assist players after a few guesses.
- hotfix: Fixed random-number generation to include the maximum value in the possible range.
- documentation: This contains the project README and a summary of the Git workflow.

## Implemented Features

This is a complete game that contains the following:

- Making a random guess between 1 and 100.
- Give feedback if the guess is too high or too low.
- Using a negative number to quit the game.
- Playing again after winning or losing.
- No more than 10 tries per game.
- Information about the number of attempts left after wrong answers.
- After several guesses, hints when the player is close to the target.
- Proper random number generation with both limits.

## Git Workflow and What I Learned

### Branching and Merging

I did some work on individual branches and then merged them into `dev`.

I did a merge of dev into feature1, solved a conflict in Main.java and then fast-forward merged feature1 back to dev. I then deleted feature1 as necessary.

### Rebasing

I rebased feature2 onto dev so that it included the changes previously merged from feature1.

I solved conflicts in the Java implementation and tests, and kept both features.

### Squashing Commits

There were four commits in the `feature3` branch at the start. I squashed them together in one commit using interactive rebase with the message:

Add hint system to show proximity after 3 attempts

I then rebased `feature3` onto `dev` resolved the conflicts and merged it into `dev`.

### Integrating Features

I updated `feature2` by merging the latest `dev` changes into it. This meant merging the hint system and the max-attempts feature into `GameEngine.java` and keeping the tests from both features.

After resolving the conflicts and testing the combined features, I merged `feature2` into `dev`.

### Cherry-Picking

To apply the random-number hotfix from the `hotfix` branch to the `main` branch, I used `git cherry-pick`. I then merged the fix into the integration branch, which is the `dev` branch.

### Resolving Conflicts

I learned how to recognize the markers in Git conflicts, how to compare changes between different branches, and how to merge code without losing functionality.

I also learned that successfully resolving conflicts is not enough on its own. Changes must be compiled and passed by the project's tests.

## Testing

I used Gradle to build the application and run its automated tests:

```bash
./gradlew clean build
```

I also played the game manually to check if it quits, replays, keeps track of max attempts, keeps track of remaining attempts, provides hints, and gives a win on the last allowed attempt.

To run the game:

```bash
./gradlew run --console=plain -q
```
## Conclusion

This assignment gave me an insight into how Git facilitates teamwork by using separate feature branches, controlled integration, history management and conflict resolution. It also taught me the significance of testing after combining various features into the same application.