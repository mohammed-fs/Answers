# Quiz
## I (Open question)
#### In the context of Github Actions, what’s a workflow? How does it take form on Github and on you repository?
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
* runs-on
* container
* env
* with
* ~~in~~

## III (Open question)
#### When talking about CI/CD, what’s an artifact? Why is it important for the continuous deployment part of a CI/CD workflow?
– In CI/CD systems, artifacts refer to the output of your build process that you would deploy. This could be a jar, tar or binary. You then deploy these artifacts onto your production servers.\
– For pushes and pull requests, GitHub stores artifacts for 90 days. The retention period for a pull request restarts each time someone pushes a new commit to the pull request.\
##### <ins>These are some of the common artifacts that you can upload:</ins>
• Log files and core dumps \
• Test results, failures, and screenshots \
• Binary or compressed files \
• Stress test performance output and code coverage results \

– Artifacts enable you to share data between jobs in a workflow and store data once completed. \
– Artifacts allow you to persist data after a job has complete and share that data with same workflow.

## IV (Open question)
#### Why is a versioning tool like git so indispensable for CI/CD?
VCS tools is a vital link between development and deployment, 
and a key component of continuous integration/continuous deployment (CI/CD) pipelines. A VCS is usually the place where the CI in CI/CD begins. \
The VCS creates the source code of record and organizes it for the build. \
<ins>Branching workflows</ins> feature that VCS provide let you tackle thorny bugs, try out new technologies, or just start coding a new feature from scratch without the risk that your changes will prevent your teammates from forging ahead with their own tasks.
