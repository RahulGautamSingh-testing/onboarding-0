# onboarding-0

This repo only has a readme file and will house links to other test repos that will be used to perform a series of tests to check the new onbaording logic.
The new onboarding logic has 2 new components :

## Tests on PRs created using new logic

- Creates an onboarding PR
- Adds a comment when onboarding PR is closed
- Detects that onboarding PR is merged and deletes onboarding cache
- Updates PR body when baseBranch is updated
- Updates PR body when onboarding branch is modified
- Adds a comment when onboarding branch is conflicted and skip processing the onboarding branch

## Tests on PRs created existing logic ie. runs on existing onboaridng PRs

- Updates the onboarding cache when run on an existing PR
- Adds a comment when onboarding PR is closed
- Detects that onboarding PR is merged and deletes onboarding cache
- Updates PR body when baseBranch is updated
- Updates PR body when onboarding branch is modified
- Adds a comment when onboarding branch is conflicted and skip processing the onboarding branch

## Miscellaneous

- dryRun
- cache: disabled
