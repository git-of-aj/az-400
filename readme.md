## Boards
- Azure Boards TOC (ms docs) :https://learn.microsoft.com/en-us/azure/devops/boards/?view=azure-devops
- [azure Boards labs](https://azuredevopslabs.com/labs/azuredevops/agile/)
https://learn.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops
1. Epic: Feature to Deliver (Goal)
2. Backlogs: Work needed to do
3. Sprints: time frame (1-2 week)
4. Work items: 1 story => collections of task
- work items to track features and requirements you're developing, code defects or bugs, and issues or risks to your project. Each work item is based on a work item type that determines the work item fields available for tracking information. The work item types available to you differ depending on the process used when your project was created: Agile, Basic, Scrum, or CMMI.
6. Tasks: Anything that helps in achieving Motive
described in Epic example: creating a DR Site
6.Bug:
7. user Story: Client's Requirement

- how ms plans with devops - https://learn.microsoft.com/en-us/devops/plan/how-microsoft-plans-devops
- Stages for Delivery:
`Dev => Test => SIT => UAT => pre-Prod => Prod`
## Git and Github
- github with azure boards - https://learn.microsoft.com/en-us/azure/devops/boards/github/?view=azure-devops
1. commit / pull requests can be added => but b4 that boards <=> github ELSE ERROR 🚫
- `merge conflict`: Merge conflicts in Git occur when two different branches have made changes to the same part of a file, and Git doesn't know which changes to keep.
- NOT RECOMMENDED : `Overwriting Git history` means making changes to commits that have already been pushed to a shared repository. This could include modifying commit messages, removing or adding commits, or even reordering commits in the history. It's done using commands like git commit --amend, git rebase, or git filter-branch.
- git LFS (LARGE FILE STORAGE) => FREE GITHUB ONLY 2 GB MAX FILE SIZE : https://docs.github.com/en/repositories/working-with-files/managing-large-files/configuring-git-large-file-storage
