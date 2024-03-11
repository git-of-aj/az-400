----------------------------------------------------------
Redhat = https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/chap-managing_services_with_systemd
-------------------------------------------------------------------

Whereas reverting is designed to safely undo a public commit, git reset is designed to undo local changes to the Staging Index and Working Directory. Because of their distinct goals, the two commands are implemented differently: resetting completely removes a changeset, whereas reverting maintains the original changeset and uses a new commit to apply the undo.

> To review, git reset is a powerful command that is used to undo local changes to the state of a Git repo. Git reset operates on "The Three Trees of Git". These trees are the Commit History (HEAD), the Staging Index, and the Working Directory. There are three command line options that correspond to the three trees. The options --soft, --mixed, and --hard can be passed to git reset

Second, git revert is able to target an individual commit at an arbitrary point in the history, whereas git reset can only work backward from the current commit

# USe Your agent In pipeline:
```yml
 name: az400m03l03a-pool
 demands:
 - Agent.Name -equals az400m03-vm0
```

Trigger pipeline when change to specific paths - 
```yml
 trigger:
   branches:
     include:
     - main
   paths:
     include:
     - src/web/*
```

## Branching strategy
- [MS RECOMMENDtions](https://learn.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops)

## deployment strategies
[Medium](https://medium.com/@navya.cloudops/devops-zero-to-hero-day-20-deployment-strategies-e6712b4801e4)
[AWS](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/deployment-strategies.html)

## Project Settings 
Teams => Include Users, Teams => Project group 'MacTraining Team' cannot be added to group 'tst', it is from a different project.
- MS DOCS => https://learn.microsoft.com/en-us/azure/devops/organizations/settings/about-settings?view=azure-devops
## Boards
- Azure Boards TOC (ms docs) : https://learn.microsoft.com/en-us/azure/devops/boards/?view=azure-devops
- [azure Boards labs](https://azuredevopslabs.com/labs/azuredevops/agile/)
- `FEATURE ==> EPIC ==> USER STORY {hierarchy}`
- Agile is philosophy scrum is a proven methodology based on agile. Here Nonheirachy, Senior engineer, Junior all work together no hierarchy 
https://learn.microsoft.com/en-us/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops
1. Epic: Feature to Deliver (Goal)
2. Backlogs: `(user story to do in a particular sprint)` Work needed to do in a sprint
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

## TFVC vs GIT 
TFVC is a centralized version control system. Typically, team members have only one version of each file on their dev machines. Historical data is maintained only on the server. Branches are path-based and created on the server.

Git: Git is a distributed version control system. Git repositories can live locally (on a developer’s machine). Each developer has a copy of the source repository on their dev machine. Developers can commit each set of changes on their dev machine and perform version control operations such as history and compare without a network connection.

> When you make changes to your files, Git will record the changes in the local repository. You can select the changes that you want to commit by staging them. Commits are always made against your local Git repository, so you don’t have to worry about the commit being perfect or ready to share with others. You can make more commits as you continue to work and push the changes to others when they are ready to be shared.

**In centralised Repo, merge b4 comit** => https://www.toptal.com/software/trunk-based-development-git-flow

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

⚠️⚠️⚠️ WHY DIFFERENT FEATURE BRANCHES??  A traditional application has one release pipeline that is shared among many teams. This process often introduces bottlenecks. When teams have the authority to move fast, they can release new features continuously, often several times per day.

The way you operate an application that releases multiple times a day is different from one that releases once or twice a year. Under a DevOps model, development and operations teams take ownership of service with shared responsibility. Through a combination of cultural philosophies, practices, and tools, they find ways to deliver applications and services at high velocity.  
 

![image](https://github.com/Ananyojha/az-400/assets/76782360/5f9c054a-72db-49c9-89a1-fe7d89166185)

# Pipeline
- run test pipeline b4 merge pr to auto test :
To trigger the pipeline on pull request merge, you can use the "Build Validation" feature:
1. `AZ CLI Commnds` - [Sample Scripts](https://github.com/Azure-Samples/azure-cli-samples/blob/master/app-service/deploy-deployment-slot/deploy-deployment-slot.sh)
2. `AZ WEBAPP UP ` - https://learn.microsoft.com/en-us/cli/azure/webapp?view=azure-cli-latest#az-webapp-up

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
## SOnarcloud Repo:
```sh
 https://github.com/SonarSource/sonar-scanning-examples.git
```
- [Lab](https://azuredevopslabs.com/labs/vstsextend/sonarcloud/)
## Mend Demo Generator - 
- [Lab](https://azuredevopslabs.com/labs/vstsextend/whitesource/)
