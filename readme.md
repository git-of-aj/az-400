## DAST vs SAST
| SAST | DAST | 
| --- | ---| 
| have access to your code (runs test on it) | Don't have access to code (tests running app) |
| helps find source code security flaws early in dev (open box testing form) | form of closed box testing - imposing like a maclicious actor wanna break into app |

SAST:
1. Sonarqube
2. GitHub Advanced Security - CodeQL
3. Gitlab SAST
4. ESLint
5. Bandit
6. OWASP dependency check
7. Trivy (Container image scanning)

DAST
1. OWASP ZAP
2. Burpsuite
3. Checkmarx
4. Wapiti
5. Arachni

![image](https://github.com/user-attachments/assets/5e46eb9e-2ee8-42c8-ae09-7abb62051d67)

## Basics
- CI (Continuous Integration) focuses on integrating and testing code frequently, ensuring that the code is always in a working state before it’s merged.
- CD (Continuous Delivery) ensures that the code can be automatically deployed to production after passing all tests, but it often requires manual approval before pushing to production.
- Continuous Deployment automates the entire process, including production deployment, without manual approval.
- In GitOps, Git serves as the central hub for managing both applications and infrastructure. Changes are committed to Git, and automated tools apply those changes to the environment, ensuring that the infrastructure matches the desired state. This approach promotes version-controlled, declarative infrastructure, and simplifies operations by making deployments and rollbacks automatic. It’s ideal for teams looking to reduce manual operations and increase deployment reliability, especially in cloud-native and Kubernetes environments

## DevSecOps
DevSecOps is all about integrating security throughout the development process, ensuring that security is automated, continuous, and part of the DevOps pipeline.

To implement DevSecOps in a production environment:

- Automate security tests in the CI/CD pipeline (SAST, DAST, SCA).
- Manage security as code with tools like OPA or Sentinel.
- Monitor production environments for anomalies and implement automated incident response.
- Secure the infrastructure (e.g., Kubernetes, cloud environments, containers).
- Foster collaboration among developers, security teams, and operations to make security a shared responsibility.

**1. Integrate Security into the CI/CD Pipeline:**
steps:
- Static Application Security Testing (SAST): Run static code analysis on your codebase for vulnerabilities, insecure coding practices, and compliance issues before the code is even committed.

> Tools: SonarQube, Checkmarx, Fortify.
- Dynamic Application Security Testing (DAST): Perform dynamic security testing on your running application in your staging or test environments to identify runtime vulnerabilities such as SQL injection, XSS, etc.

> Tools: OWASP ZAP, Burp Suite, Acunetix.
- Software Composition Analysis (SCA): Scan dependencies (open source libraries, frameworks) for known vulnerabilities, outdated libraries, or licensing issues.

> Tools: Snyk, Dependabot, WhiteSource.
- Infrastructure as Code (IaC) Security: Implement security checks for infrastructure code (e.g., Terraform, CloudFormation) to ensure that your infrastructure is secure by design.

> Tools: Checkov, Terraform Sentinel, Prowler.
- Secret Scanning: Automatically scan code for exposed secrets like API keys, database passwords, or access tokens that might have been accidentally committed.

> Tools: TruffleHog, GitLeaks.
**2. Implement Security and Compliance as Code**:
DevSecOps aims to manage and enforce security policies as code, enabling teams to ensure compliance and security automatically in each deployment.
> Azure Policy or hashicorp sentinel
**3. Security Monitoring and Incident Response**
DevSecOps isn't just about preventing vulnerabilities but also about monitoring and responding to security incidents.

steps:
- Continuous Monitoring: Use security monitoring tools to continuously watch for security threats and anomalies in your production environment (e.g., unauthorized access, DDoS attacks, compromised containers).

> Tools: Prometheus, Grafana, ELK Stack.
- Intrusion Detection and Prevention: Set up intrusion detection/prevention systems (IDS/IPS) to detect any abnormal activity in real time. Tools like Wazuh and Snort can help with this.
Centralized Logging: Collect logs from your application, infrastructure, and security systems in a centralized location for real-time analysis and easy access during security investigations.

> Tools: Splunk, ELK Stack (Elasticsearch, Logstash, Kibana).
- Automated Incident Response: When an anomaly or threat is detected, integrate automated responses such as shutting down suspicious containers, blocking IP addresses, or triggering alerts to your security team.

> Tools: AWS GuardDuty, Azure Sentinel, Kubernetes RBAC policies.

**4. Environment security - fw etc**
**5. Contiuous feedback and training**

### Key Principles of DevSecOps
1. Shift Left:
The idea behind "shift left" is to bring security testing earlier in the SDLC. Rather than waiting until production, security vulnerabilities are identified and addressed as part of the development and testing process.

2. Automation:
Security checks, such as static code analysis, dynamic testing, and dependency scanning, are automated and embedded into the CI/CD pipeline. Automation helps ensure consistent and efficient security controls.

3. Collaboration:
DevSecOps fosters a culture where developers, security experts, and operations teams work together throughout the lifecycle, reducing friction and making security everyone's responsibility.

4. Continuous Monitoring:
Security is not a one-time activity. DevSecOps emphasizes the need for continuous monitoring of the infrastructure and application environment, detecting vulnerabilities or intrusions in real time.

5. Compliance as Code:
Security and compliance requirements are managed as code. This allows teams to maintain a clear and versioned record of security policies and configurations, which can be automated, versioned, and checked throughout the lifecycle.

6. Minimize Human Intervention:
By automating the security processes and integrating them into the CI/CD pipeline, DevSecOps reduces the reliance on manual checks and human intervention, which can often lead to errors and vulnerabilities.

migrate from classic to yaml -!https://learn.microsoft.com/en-us/azure/devops/pipelines/migrate/from-classic-pipelines?view=azure-devops
- secure file
- [approvals](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/approvals?view=azure-devops&tabs=check-pass)

- [GitHub Advanced Security](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features?view=azure-devops&tabs=yaml)
- [Defender for DevOps](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-devops-introduction)
- DEFENDER FOR DEVOPS :  multi-pipeline environments, including Azure DevOps, GitHub, and GitLab. DevOps security recommendations can then be correlated with other contextual cloud security insights to prioritize remediation in code. 
----------------------------------------------------------
Redhat = https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/chap-managing_services_with_systemd
-------------------------------------------------------------------
[ASP.Net Feature Flag App service demo](https://learn.microsoft.com/en-us/azure/azure-app-configuration/quickstart-feature-flag-aspnet-core)

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

# Area Path boards - 
- Area paths allow you to group work items by team, product, or feature area. Iteration paths allow you to group work into sprints, milestones, or other event-specific or time-related period. Both these fields allow you to define a hierarchy of paths.
- Add areas when you have these requirements:

1. Filter queries based on a product or feature area
2. Organize or group work items by team or subteams
3. Restrict access to work items based on their area.

* Area paths help in organizing work items based on different functional areas of the mobile app.
* Iterations provide a timeboxed framework for planning and executing work in short cycles.
* Backlog items represent `bundle of deliverables in a sprint` the overall work to be done, prioritized and selected for inclusion in specific iterations based on business value and team capacity.

> Teams build the sprint backlog during the sprint planning meeting, typically held on the first day of the sprint
> he product owner works with the team to identify those stories or backlog items to complete in the sprint.

`Capacity = 1 : this represents 1 hour of development work per day`
Planning meetings typically consist of two parts. In the first part, the team and product owner identify the backlog items that the team feels it can commit to completing in the sprint, based on experience with previous sprints. These items get added to the sprint backlog. In the second part, the team determines how it will develop and test each item. They then define and estimate the tasks required to complete each item. Finally, the team commits to implementing some or all the items based on these estimates.
 -----------
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
