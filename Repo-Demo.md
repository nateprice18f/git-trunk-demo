# Repo Git trunk-based development demo

This is a very basic example and DOES not cover all the complexities of a project. You might need to handle merge conflicts or use other git features depending on your specific needs. Always make sure to keep your branches up-to-date with the latest changes from the trunk (main branch) to avoid large, difficult merges.

## Demo

Simple example of how you might use git for trunk-based development with two release branches for version 1 and version 2. In this demo; shows how two features (feature1 and feature2) are created and then merged back into the version branches using release tags.

# Create a new repository 
```
git init 
```

# Create a new file and add it to the repository 
```
echo "Initial commit" > file.txt
git add file.txt
```
 
# Commit the changes to the main branch 
```
git commit -m "Initial commit" 
```

# Create two feature branches 
```
git branch feature1
git branch feature2
```
 
# Switch to the first feature branch and make some changes 
```
git checkout feature1
echo "Feature 1" > feature1.txt
git add feature1.txt
git commit -m "Add Feature 1"
```

# Switch to the second feature branch and make some changes 
```
git checkout feature2 
echo "Feature 2" > feature2.txt 
git add feature2.txt 
git commit -m "Add Feature 2" 
```
 
# Merge the first feature branch back into main with a release tag 
```
git checkout main 
git merge --no-ff feature1 -m "Merge Feature 1 into Main" 
git tag v1.0.0 
```
 
# Merge the second feature branch back into main and publish the release 
```
git merge --no-ff feature2 -m "Merge Feature 2 into Main" 
git tag v1.1.0 
git push --tags origin main
```

# Push all local commits to remote  
```
git push -all
```