- You can make more commits as you continue to work and push the changes to others when they are ready to be shared.

- Git commits consists of the following:

- The file(s) changed in the commit. Git keeps the contents of all file changes in your repo in the commits. This keeps it fast and allows intelligent merging.
A reference to the parent commit(s). Git manages your code history using these references.
A message describing a commit. You give this message to Git when you create the commit. It’s a good idea to keep this message descriptive, but to the point.

https://learn.microsoft.com/en-us/azure/devops/organizations/settings/about-teams-and-settings?view=azure-devops


- Committing changes to a branch will not affect other branches and you can share branches with others without having to merge the changes into the main project.

- Git does not create multiple copies of your source when working with branches, but rather uses the history information stored in commits to recreate the files on a branch when you start working on it.

- Auto complete ewhen requiremts met

- git merge - command lets you take the independent lines of development created by git branch and integrate them into a single branch.

git checkout 
git branch -d for deleting 

- If Git encounters a piece of data that is changed in both histories it will be unable to automatically combine them. This scenario is a version control conflict and Git will need user intervention to continue. 

git status
git checkout 
git pull / fetch

- fast forward via rebase for hotfix / small change / small featue

- common place were both branch history meet

- the two branches you're trying to merge both changed the same part of the same file, Git won't be able to figure out which version to use

- Feature branches should have descriptive names,

- git cherry-pick can be useful for undoing changes. For example, say a commit is accidently made to the wrong branch. You can switch to the correct branch and cherry-pick the commit to where it should belong.

useful tool but not always a best practice. Cherry picking can cause duplicate commits
```
a - b - c - d   Main
         \
           e - f - g Feature
```

Originally f was in other 
```
 a - b - c - d - f   Main
         \
           e - f - g Feature
```

- Git hooks are scripts that run automatically every time a particular event occurs in a Git repository. They let you customize Git’s internal behavior and trigger customizable actions at key points in the development life cycle.

1. remove (.)sample
2. make it executable

- hooks for a team of developers can be a little tricky because the .git/hooks directory isn’t cloned with the rest of your project, nor is it under version control.
create a template dir https://git-scm.com/docs/git-init#_template_directory

