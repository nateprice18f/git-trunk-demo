# Simple Feature Development with Release Tags

This example assume that you're working directly on the main branch as your 'trunk'. 
Adjust as necessary for the team's workflow. Remember, the key idea behind trunk-based development is that all developers work on a single branch and integrate their changes often, ideally several times a day. This helps catch integration issues early and reduces the complexity of merges.

## Developer starts working on a new feature
``` git checkout main ```
``` git pull origin main ```
``` git checkout -b new-feature ```

## Developer makes changes and commits them
``` git add . ```
``` git commit -m "Add new feature" ```

# Developer pushes feature branch to remote
``` git push origin new-feature ```

## After code review, the feature is merged into main
``` git checkout main ```
``` git pull origin main ```
``` git merge new-feature ```
``` git push origin main ```

## Tag the new release version
 ``` git tag -a v1.0 -m "First version release" ```
``` git push origin v1.0 ```