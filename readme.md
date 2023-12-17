## Project Settings 
Teams => Include Users, Teams => Project group 'MacTraining Team' cannot be added to group 'tst', it is from a different project.
- MS DOCS => https://learn.microsoft.com/en-us/azure/devops/organizations/settings/about-settings?view=azure-devops
## Boards
- Azure Boards TOC (ms docs) : https://learn.microsoft.com/en-us/azure/devops/boards/?view=azure-devops
- [azure Boards labs](https://azuredevopslabs.com/labs/azuredevops/agile/)
https://learn.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops
1. Epic: Feature to Deliver (Goal)
2. Backlogs: Work needed to do
3. Sprints aka Iteration Path: time frame (1-2 week or 2-4 week): Iteration Paths, also referred to as sprints, support assignment of work items to time-box intervals. You define iteration paths at the project level, and then each team selects the paths that they want to use.
4. Work items: 1 story => collections of task
- work items to track features and requirements you're developing, code defects or bugs, and issues or risks to your project. Each work item is based on a work item type that determines the work item fields available for tracking information. The work item types available to you differ depending on the process used when your project was created: Agile, Basic, Scrum, or CMMI.
6. Tasks: `Smallest Measurable unit of work`Anything that helps in achieving Motive
described in Epic example: creating a DR Site
6.Bug:
7. user Story: `A complete cycle of users behaviour. what to see post login` Client's Requirement

* [Cycle Time in dashboards](https://learn.microsoft.com/en-us/azure/devops/report/dashboards/cycle-time-and-lead-time?toc=%2Fazure%2Fdevops%2Fboards%2Ftoc.json&view=azure-devops)
1. Lead Time: planning to delivery full time
2. cycle time: my team strated taking action & delivered in ...... time
* [WIki Azuer Boards](https://learn.microsoft.com/en-us/azure/devops/project/wiki/wiki-create-repo?view=azure-devops&tabs=browser)
* [service hook](https://learn.microsoft.com/en-us/azure/devops/service-hooks/overview?toc=%2Fazure%2Fdevops%2Fmarketplace-extensibility%2Ftoc.json&view=azure-devops)
- how ms plans with devops - https://learn.microsoft.com/en-us/devops/plan/how-microsoft-plans-devops
- Stages for Delivery:
`Dev => Test => SIT => UAT => pre-Prod => Prod`
## Git and Github
- github with azure boards - https://learn.microsoft.com/en-us/azure/devops/boards/github/?view=azure-devops
1. commit / pull requests can be added => but b4 that boards <=> github ELSE ERROR 🚫
2. In Github Commit make commit message as `AB#ID` ID = ID of work Item ==> https://learn.microsoft.com/en-us/azure/devops/boards/github/link-to-from-github?view=azure-devops
- `merge conflict`: Merge conflicts in Git occur when two different branches have made changes to the same part of a file, and Git doesn't know which changes to keep.
- NOT RECOMMENDED : `Overwriting Git history` means making changes to commits that have already been pushed to a shared repository. This could include modifying commit messages, removing or adding commits, or even reordering commits in the history. It's done using commands like git commit --amend, git rebase, or git filter-branch.
- git LFS (LARGE FILE STORAGE) => FREE GITHUB ONLY 2 GB MAX FILE SIZE : https://docs.github.com/en/repositories/working-with-files/managing-large-files/configuring-git-large-file-storage

## Repo 
`git clone –depth [depth] [clone-url]`

In centralised Repo, merge b4 comit => https://www.toptal.com/software/trunk-based-development-git-flow

![image](https://github.com/Ananyojha/az-400/assets/76782360/d52daf80-33d6-4f23-8920-7aa1cc9dfa03)

### Dev Styles
1. Git flow: 1 master barnch => feature branch => bug branches => merge them =>  strict control. Only authorized developers can approve changes after looking at them closely. It ensures code quality and helps eliminate bugs early.
* very slow dev
* pull request focus on new code not whole

1. Repo => commits shows Graph what merged where?

- On the bottom of the branch policies page you can select Automatically included reviewers. Click the + button to add reviewers. When adding the reviewers you can select if these selected reviewers are required or optional. This is actually something of a rule-builder, you can add multiple 'rules' by repeatedly going through click + and add reviewers

https://stackoverflow.com/questions/64754998/how-do-i-add-a-required-reviewer-when-people-of-a-given-team-create-a-pull-reque

`Project settings => Notifications => new settings => + Subscription => code` => 
https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-request-notifications?view=azure-devops

- run test pipeline b4 merge pr to auto test :
To trigger the pipeline on pull request merge, you can use the "Build Validation" feature:

- In the branch policies settings, under "Build Validation," click on "Add build policy."
2. Select your YAML pipeline from the list of available builds.
3. Configure the "Build expiration" and other options as needed.

- you checkout to repo root !

```yml
trigger:
- main
- test
# triggers when you create, update anything on pull request
pr:
- '*'
pool:
# Name of Self Hosted Agnet Pool 
  name: Default
```
