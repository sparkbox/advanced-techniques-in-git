# Advanced Techniques in Git

This is a small repository to practice your skills with rebasing, interactive rebasing, and commit curation.

## Challenges

### Rebasing

[Rebasing] is the process of taking one branch and placing its changes at the end of the changes of a different branch.

1. Checkout the branch `feat--add-over-the-rainbow`.
1. See how there are changes in `main` that are not yet in `feat--add-over-the-rainbow`.
1. Run `git rebase main` to base the `feat--add-over-the-rainbow` branch on `main`.

- [ ] Confirm that `feat--add-over-the-rainbow` is based off of the latest changes in `main`.

### Interactive Rebasing

[Interactive rebasing] is the process of modifying history by editing one commit at a time.

1. Checkout the branch `feat--add-beauty-and-the-beast`.
1. See how each lyric is added one line at a time. Use interactive rebasing (`git rebase -i main`) to see all the commits in this branch that are not in `main`.
1. While in interactive rebasing, reorder the commits so each commit adds one line at a time in order. Since this will cause merge conflicts, try moving only one commit at a time. When resolving conflicts, ask yourself "what would this commit look like had I made this commit in this order.

- [ ] Confirm that commits in `feat--add-beauty-and-the-beast` are ordered by the order of the lyric.
- [ ] Confirm that each commit in `feat--add-beauty-and-the-beast` only contains the contents of that specific commit and is free of merge conflicts.

### Curated Commits

By curating your commits before submitting a PR, you can help onboard your reviewer by creating a narrative that is independent from your chronology of changes. This means that, before submitting a PR, you can use interactive rebasing to reorganize your commits to create a narration that reduces noise and guides the reviewer through your thinking and thought process.

1. Checkout the branch `feat--add-frozen-moana-princess-and-frog`.
1. Look thought the commits of this branch and imagine you were assigned to review it commit-by-commit. Instead of having a linear history that guides the reviewer through the changes, the history is a bit erratic.
1. Using interactive rebasing (`git rebase -i main`), make the following changes:

- [ ] Move any bug fixes **unrelated to this branch** to the beginning of this history (to separate it from the features of this branch).
- [ ] Fix up any bug that were created **within** this branch to the commit that introduced the bug (if there's no value in the reviewer seeing it).

### Cherry Picking

You can use [cherry picking] to copy the contents of individual commits from one branch into another branch. This is an especially useful tool when commits are made in the wrong branch or in a temporary branch.

1. Checkout the branch `feat--add-frozen-2`.
1. Locate the commit made in this branch. We want to cherry pick this commit on the `feat--add-frozen-moana-princess-and-frog` branch. Copy the commit SHA and switch to to the target (`feat--add-frozen-moana-princess-and-frog`) branch.
1. Using cherry pick (`git cherry-pick`), make the following changes:

- [ ] Copy the commit from `feat--add-frozen-2` to `feat--add-frozen-moana-princess-and-frog`.
- [ ] Use the cherry pick command (`git cherry-pick`) following by the SHA to apply the changes from `feat--add-frozen-2` to `feat--add-frozen-moana-princess-and-frog`.

### Git Revert

You can [revert] changes of a commit to undo specific changes without disrupting the history of the production branch. This is different than dropping a commit because it retains the history of both making changes and undoing them.

1. Checkout the branch `feat--add-over-the-rainbow`. This branch should have been rebased on `main` in the first challenge.
1. Merge `feat--add-over-the-rainbow` into `main` using the `--ff-only` flag.
1. While on `main`, locate the commit SHA for the merge in the last step.
1. Run `git revert` followed by the SHA in the previous step to revert the merge.

- [ ] Confirm the merge from `feat--add-over-the-rainbow` and the subsequent revert is represented in the history of `main`.

## Branch Diagram

The following diagram shows the relationship between all challenge branches and the `main` branch.

![Branch Diagram](/assets/Branch_Diagram.png)

[Rebasing]: https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase
[Interactive rebasing]: https://www.atlassian.com/git/tutorials/rewriting-history#git-rebase-i
[cherry picking]: https://www.atlassian.com/git/tutorials/cherry-pick
[revert]: https://www.atlassian.com/git/tutorials/undoing-changes/git-revert
