# Handling Merge Conflicts with Release Tags

This example assume that you're working directly on the main branch as your 'trunk'. 
Adjust as necessary for the team's workflow. Remember, the key idea behind trunk-based development is that all developers work on a single branch and integrate their changes often, ideally several times a day. This helps catch integration issues early and reduces the complexity of merges.

## Developer starts working on a new feature
``` git checkout main ```
``` git pull origin main ```
``` git checkout -b new-feature ```

## Developer makes changes and commits them
``` git add . ```
``` git commit -m "Add new feature" ```

## Developer pulls latest changes from main before merging
``` git checkout main ```
``` git pull origin main ```

## If there are merge conflicts when attempting to merge the feature
``` git merge new-feature ```

## Resolve conflicts, then commit and push changes to main
``` git add . ```
``` git commit -m "Resolve merge conflicts" ```
``` git push origin main ```

## Tag the new release version after resolving conflicts
``` git tag -a v1.1 -m "Second version release after resolving conflicts" ```
``` git push origin v1.1 ```