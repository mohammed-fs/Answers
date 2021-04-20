# Quiz
## I (Open question)
#### In the context of Github Actions, what’s a `workflow`? How does it take form on Github and on you repository?
* A workflow is a configurable automated process made up of one or more jobs. 
* Workflow files use YAML syntax, and must have either a .yml or .yaml file extension. 
* workflow supports teams and projects where deployments are made regularly.
* GitHub Actions is a CI/CD and general automation system introduced by GitHub in 2018. 
* It is integrated right into GitHub and enabled by default in every GitHub repository.
* Every GitHub repository can contain one or more workflows. 
* Each workflow is defined in a separate YAML in the .github/workflows directory of the repo. 
* Multiple workflows may run at the same time in parallel.

## II (Multiple choices)
#### Find and strikethrough the invalid key(s) for the Github workflow syntax in the list below:
* `runs-on`
* `container`
* `env`
* `with`
* ~~`in`~~

## III (Open question)
#### When talking about CI/CD, what’s an `artifact`? Why is it important for the continuous deployment part of a CI/CD workflow?
* In CI/CD systems, artifacts refer to the output of your build process that you would deploy. This could be a jar, tar or binary. You then deploy these artifacts onto your production servers.
* For pushes and pull requests, GitHub stores artifacts for 90 days. The retention period for a pull request restarts each time someone pushes a new commit to the pull request.
#### <ins>These are some of the common artifacts that you can upload:</ins>
• Log files and core dumps \
• Test results, failures, and screenshots \
• Binary or compressed files \
• Stress test performance output and code coverage results 

– Artifacts enable you to share data between jobs in a workflow and store data once completed. \
– Artifacts allow you to persist data after a job has complete and share that data with same workflow.

## IV (Open question)
#### Why is a versioning tool like `git` so indispensable for CI/CD?
VCS tools is a vital link between development and deployment, 
and a key component of continuous integration/continuous deployment (CI/CD) pipelines. A VCS is usually the place where the CI in CI/CD begins. \
The VCS creates the source code of record and organizes it for the build. \
<ins>Branching workflows</ins> feature that VCS provide let you tackle thorny bugs, try out new technologies, or just start coding a new feature from scratch without the risk that your changes will prevent your teammates from forging ahead with their own tasks.

## V (Open question)
#### In the context of Github Actions, what’s a `runner`? What type of `runner` can you find/use?
It is a machine that has a target operating system (OS) as well as a set of software and/or tools you may desire for completing your job.   
GitHub provides a set of these pre-configured runners that you are using when you use the runs-on label and use any one of the combination of: windows-latest, ubuntu-latest (or ubuntu-18.04 or ubuntu-16.04), macosx-latest.

## VI (Open question)
#### Can you change the configuration of an `hosted runner`? What do you need to do if none of the `hosted runner` meet your needs?
Yes. create and host self-hosted runner, Self-hosted runners offer more control of hardware, operating system, and software tools than GitHub-hosted runners provide. With self-hosted runners, you can choose to create a custom hardware configuration with more processing power or memory to run larger jobs, install software available on your local network, and choose an operating system not offered by GitHub-hosted runners. Self-hosted runners can be physical, virtual, in a container, on-premises, or in a cloud.

## VII (Open question)
#### Describe (in your own words) what the workflow below does with as much details as possible.
```Yaml
name: Mark stale issues and pull requests

on:
  schedule:
  - cron: "30 1 * * *"

jobs:
  stale:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/stale@v1
      with:
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        stale-issue-message: 'Stale issue message'
        stale-pr-message: 'Stale pull request message'
        stale-issue-label: 'no-issue-activity'
        stale-pr-label: 'no-pr-activity'
```

<h4>name:</h4> Mark stale issues and pull requests: 
name: (refers to the name of the workflow as it will appear in the Actions tab of the GitHub repository.)

<h4>on:</h4> specifies the event that automatically triggers the workflow file. 
Such an event can, for example be a push event, so that the jobs run every time someone pushes a change to the repository. You can set up the workflow to only run on certain branches, paths, or tags. 

  <h4>schedule:</h4> (refers to how often and when the specific trigger event is fired. You can schedule a workflow to run at specific UTC times using POSIX cron syntax. Scheduled workflows run on the latest commit on the default or base branch. The shortest interval you can run scheduled workflows is once every 5 minutes. 

  - cron: "30 1 * * *"  this refers to the minute (30) hour (1) and *** for the day

<h4>jobs:</h4> 
•	composed of a collection steps, which in turn consisting of specific actions. 
•	Those actions can be shell scripts or other stand alone commands
•	Jobs are triggered by an event and
<h4>stale:</h4> 
•	is a branch that has not had any commits in the previous 3 months. 
•	This generally indicates an old/unmaintained/not current branch. ... 
•	So a "stale git branch" is generally a branch of the repository that hasn't been touched in a long time

<h4>runs-on:</h4> ubuntu-latest 
•	(Configures the job to run and be executed on the latest fresh virtual machine (container)
•	based on Ubuntu Linux OS based runner hosted by GitHub.) 

 <h4>Steps:</h4> 
•	(specify or define the order in which actions and commands are executed in order  to fulfil a job; 
•	they contain a collection of actions, that enable you accomplish the specified job.)
    - uses: actions/stale@v1 => refers to the version of the stale
      with:  => specifies the attributes of token, message and label this step is going to use, as follows
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        stale-issue-message: 'Stale issue message'
        stale-pr-message: 'Stale pull request message'
        stale-issue-label: 'no-issue-activity'
        stale-pr-label: 'no-pr-activity'