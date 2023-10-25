# Multiple Dev trunk-based development

This is a simplified example and actual workflows may vary based on the team's needs and preferences. For instance, you might use pull requests for merging changes, handle merge conflicts, use a develop branch instead of merging directly into the release branch, etc. Also remember to regularly fetch and merge/rebase to stay up-to-date with the remote repository if you are working in a team.

Basic example of how you might set up a git repository for trunk-based development with two release branches (version 1 and version 2), and how three developers could work on the same feature branch and merge changes into version 1.

First, initialize the git repository and create two branches for the releases:
```
git init
git commit --allow-empty -m "Initial commit"
git branch release/v1
git branch release/v2
```

Next, let's say we have three developers: Dev1, Dev2, and Dev3. They are all working on a feature called feature1. They would each create their own feature branches from release/v1 like so:

# Dev1
```git checkout -b Dev1/feature1 release/v1```

# Dev2
```git checkout -b Dev2/feature1 release/v1```

# Dev3
```git checkout -b Dev3/feature1 release/v1```

They would each do their work in their respective branches and commit their changes:

# Dev1
```
echo "Dev1's changes" > Dev1.txt
git add Dev1.txt
git commit -m "Dev1's changes"
```
# Dev2
```
echo "Dev2's changes" > Dev2.txt
git add Dev2.txt
git commit -m "Dev2's changes"
```
# Dev3
```
echo "Dev3's changes" > Dev3.txt
git add Dev3.txt
git commit -m "Dev3's changes"
```

Once each Dev's finished their part of the feature, they would merge their changes back into release/v1:

# Dev1
```
git checkout release/v1
git merge --no-ff Dev1/feature1 -m "Merge Dev1's feature1"
```

# Dev2
```
git checkout release/v1
git merge --no-ff Dev2/feature1 -m "Merge Dev2's feature1"
```

# Dev3
```
git checkout release/v1
git merge --no-ff Dev3/feature1 -m "Merge Dev3's feature1"
```

Finally, when the feature is complete and ready for release, tag the commit in release/v1:
```
git tag -a v1.0.0 -m "Release version 1.0.0"
```