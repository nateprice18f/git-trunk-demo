# Using Rebase for a Cleaner History with Release Tags

This example assume that you're working directly on the main branch as your 'trunk'. 
Adjust as necessary for the team's workflow. Remember, the key idea behind trunk-based development is that all developers work on a single branch and integrate their changes often, ideally several times a day. This helps catch integration issues early and reduces the complexity of merges.


## Developer starts working on a new feature
``` git checkout main ```
``` git pull origin main ```
``` git checkout -b new-feature ```

## Developer makes changes and commits them
``` git add . ```
``` git commit -m "Add new feature" ```

## Before merging, the developer rebases to create a linear history 
``` git checkout main ```
``` git pull origin main ```
``` git checkout new-feature ```
``` git rebase main ```

## Resolve any conflicts, then merge the feature into main 
``` git checkout main ```
``` git merge new-feature --ff-only ``` # ensures a clean, linear history
``` git push origin main  ```

## Tag the new release version after rebasing and merging 
``` git tag -a v1.2 -m "Third version release after rebasing and merging" ```
``` git push origin v1.2  ```

