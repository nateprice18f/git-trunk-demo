## Git trunk-based development 

> **Warning**
> The work done within this repo are proof of concept and should be used as a starting point for future work.

## A simple guide to trunk-based development with use of release tags.
Trunk-Based Development with GitTrunk-based development is a software development approach where all developers work on a single branch, often called 'trunk' or 'main'.

## Remember, the key to successful trunk-based development is frequent integration and avoiding long-lived branches.

### Basic Workflow
- Clone the Repository: Start by cloning the repository to your local machine using git clone.
```
git clone https://github.com/repo/repository.git
```
- Create a New Branch: Before starting work on a new feature or bug fix, create a new branch. This keeps your changes isolated until they're ready to be merged into the main branch.
```
git checkout -b feature_branch
```
- Make Changes: Make your changes to the code and commit them.
```
git add .
git commit -m "Commit message"
```
- Pull Latest Changes: Before pushing your changes, pull the latest changes from the main branch. This helps to avoid merge conflicts.
```
git checkout main
git pull
```
- Rebase Your Branch: Switch back to your feature branch and rebase it onto main. This will apply your changes on top of the changes from main.
```
git checkout feature_branch
git rebase main
```
- Resolve Conflicts: If there are any conflicts between your changes and the changes in main, Git will pause the rebase and allow you to resolve those conflicts.
- Push Changes: Once all conflicts have been resolved and all tests pass, push your changes to the remote repository.
```
git push origin feature_branch
```
- Merge into Main: Finally, create a pull request to merge your changes into main. After the pull request has been reviewed and approved, merge it into main.
- Tagging a Release: After merging significant changes or when preparing for a release, you can tag the current commit on main as a release.

``` 
git tag -a v1.0 -m "Release version 1.0"
git push origin v1.0
```
