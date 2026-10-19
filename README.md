       Number Guessing Game

Project Overview

This is a Java number guessing game that is used to practice Git branching, merging, rebasing, squashing and cherry-picking. The project uses Gradle for building and testing.

Initial Branch Structure

main: This branch contains the original version of the number guessing game and is the stable branch.

dev: This is the integration branch for combining and testing features. Initially it includes a message for players.

feature1: This branch adds quitting with a negative number, a play-again loop improved guess feedback and a version comment.

feature2: This branch introduces max number of attempts and game-over behavior.

feature3: This branch adds a hint system that gives players guidance after several attempts.

hotfix: This branch fixes the number generation so that the maximum value is included in the possible range.

Development Workflow

Features are developed in branches before being integrated into dev. The main branch is used for releases and urgent fixes.

The project also provides opportunities to practice resolving Git conflicts while preserving the behavior introduced by branches.