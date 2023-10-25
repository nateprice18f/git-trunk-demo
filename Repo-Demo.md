# Repo Git trunk-based development demo

This is a very basic example and DOES not cover all the complexities of a project. You might need to handle merge conflicts or use other git features depending on your specific needs. Always make sure to keep your branches up-to-date with the latest changes from the trunk (main branch) to avoid large, difficult merges.

## Demo

Simple example of how you might use git for trunk-based development with two release branches for version 1 and version 2. In this demo; shows how two features (feature1 and feature2) are created and then merged back into the version branches using release tags.

# Initialize a new git repository
```
git init
```
# Create an initial commit
```
echo "Initial commit" > file.txt
git add file.txt
git commit -m "Initial commit"
```

# Create two release branches for version 1 and version 2
```
git branch release/v1
git branch release/v2
```

# Create and checkout a new branch for feature1
```
git checkout -b feature1
echo "Feature 1" >> file.txt
git commit -am "Add feature 1"
```

# Merge feature1 into release/v1 and tag it
```
git checkout release/v1
git merge feature1 -m "Merge feature 1 into v1"
git tag v1.1
```

# Merge feature1 into release/v2 and tag it
```
git checkout release/v2
git merge feature1 -m "Merge feature 1 into v2"
git tag v2.1
```

# Create and checkout a new branch for feature2
```
git checkout -b feature2
echo "Feature 2" >> file.txt
git commit -am "Add feature 2"
```

# Merge feature2 into release/v1 and tag it
```
git checkout release/v1
git merge feature2 -m "Merge feature 2 into v1"
git tag v1.2
```

# Merge feature2 into release/v2 and tag it
```
git checkout release/v2
git merge feature2 -m "Merge feature 2 into v2"
git tag v2.2
```

# Now, you have two versions of your software with different features in different branches.