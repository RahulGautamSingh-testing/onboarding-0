# onboarding-0

This repo only has a readme file and will house links to other test repos that will be used to perform a series of tests to check the new onbaording logic.
The new onboarding logic has 2 new components :

## Tests on PRs created using new logic

- Creates an onboarding PR (https://github.com/RahulGautamSingh-testing/onboarding-1.1)
- Adds a comment when onboarding PR is closed https://github.com/RahulGautamSingh-testing/onboarding-1.1/pull/1
- Detects that onboarding PR is merged and deletes onboarding cache https://github.com/RahulGautamSingh-testing/onboarding-1.1/pull/2
```log
DEBUG: Repo is onboarded (repository=RahulGautamSingh-testing/onboarding-1.1)
DEBUG: Delete Onboarding Cache (repository=RahulGautamSingh-testing/onboarding-1.1)
```
- Updates PR body when baseBranch is updated https://github.com/RahulGautamSingh-testing/onboarding-1.1/pull/1
```log
DEBUG: extract() (repository=RahulGautamSingh-testing/onboarding-1.1)
DEBUG: Cached extract result cannot be used due to base branch SHA change (old=fd998b4e0f6193cb22c973843e3c9f549281cbf7, new=9602fa525b4164a007bd07d8f909da15e56c2dfb) 
(repository=RahulGautamSingh-testing/onboarding-1.1)
```
- Updates PR body when onboarding branch is modified https://github.com/RahulGautamSingh-testing/onboarding-1.2/pull/1
```log
DEBUG: Update Onboarding Cache (repository=RahulGautamSingh-testing/onboarding-1.2)
       "onboardingCache": {
         "defaultBranchSha": "a75c1dbf81a2536058b6cd53f162581047abc44e",
         "onboardingBranchSha": "5d2ca0473ff4b457f9b2d7f8258746461755263e",
         "isConflicted": false,
         "isModified": true
       }
...
DEBUG: extract() (repository=RahulGautamSingh-testing/onboarding-1.2) // old extract-cache deleted so couldn't be feteched here
DEBUG: Setting current branch to main (repository=RahulGautamSingh-testing/onboarding-1.2)
```
- Adds a comment when onboarding branch is conflicted and skip processing the onboarding branch https://github.com/RahulGautamSingh-testing/onboarding-1.3/pull/1
```log
DEBUG: Update Onboarding Cache (repository=RahulGautamSingh-testing/onboarding-1.3)
       "onboardingCache": {
         "defaultBranchSha": "d45f86990ea6fdd7d3343625762e8cffb5349f6f",
         "onboardingBranchSha": "b001f0307b44806b1f83074f8d924ae05de6f0af",
         "isConflicted": true,
         "isModified": true
       }
```

## Tests on PRs created existing logic ie. runs on existing onboaridng PRs

- Updates/Creates the onboarding cache when run on an existing PR https://github.com/RahulGautamSingh-testing/onboarding-4/pull/1
```log
DEBUG: Create Onboarding Cache (repository=RahulGautamSingh-testing/onboarding-4)
       "onboardingCache": {
         "defaultBranchSha": "0e1fd1a394a862f3d1983f58c3654edfaebb50e7",
         "onboardingBranchSha": "179871223f8f7c09a38ce1e64ed67b75db3efb5b",
         "isConflicted": false,
         "isModified": false
       }
```
- Adds a comment when onboarding PR is closed https://github.com/RahulGautamSingh-testing/testOnboarding/pull/2#issuecomment-1515716650
- Detects that onboarding PR is merged and deletes onboarding cache(if present) https://github.com/RahulGautamSingh-testing/testOnboarding/pull/3
- Updates PR body when baseBranch is updated https://github.com/RahulGautamSingh-testing/onboarding-4/pull/1#issue-1661697175
![image](https://user-images.githubusercontent.com/99875673/233264934-f9a6e61d-7428-4fa1-9996-3fa006910e10.png)
- Updates PR body when onboarding branch is modified https://github.com/RahulGautamSingh-testing/onboarding-4/pull/1#issue-1661697175

