# onboarding-0

This repo only has a readme file and will house links to other test repos that will be used to perform a series of tests to check the new onbaording logic.
The new onboarding logic has 2 new components :
1. It merges onboarding branch into base branch 
2. It uses cache to store modified/conflicted states

The links to test repos are below. Each test repo has its own readme explaining the details of the test.

The tests:
1. Creates an onboarding PR and its cache
2. Updates cache each run
3. Falls back to git if cache invalid & update cache
4. Adds cache for existing onboarding PRs
5. Test new logic on PRs opened by old logic
6. Updates onboarding PR body when i) baseBranch updated ii) onboardingBranch modified
7. Skips conflicted branch and adds a comment
8. Seeing what happens when we run with new logiv on a old conflicted/modified branch 
9. Running on a closed onboarding PR
10. Running on a repo which merged the onboarding PR
