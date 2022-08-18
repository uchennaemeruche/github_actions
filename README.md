# Github Actions

Github Actions helps to automate the build, test and deployment pipeline of a software all within Github. With Github Actions, teams can define highly advanced pipelines.


## Workflows
Workflows refers to an automated procedure that is made up of one or more Jobs which can either run sequentially or in parallel. Workflows can be triggered by events in the repository, triggered manually or scheduled.

 ### Creating a workflow:
 A  YAML(.yml) file in the .github->workflows folder of our repository defines a workflow. 
A repository can have multiple workflows, each of which can perform different set of tasks. 

A workflow can be designated to build and test pull requests, and another to deploy  an application everytime a release is created.  
Workflows are reusable in that, they can be accessed from other workflows. Reusing workflows helps to avoid duplication of codes, thus leading to more maintanable codebase.

A workflow that uses another workflow is called a *caller* workflow. The reusable workflow is a *called* workflow.
Actions in a called Workflow reused from a different repository will run as if they were part of the caller workflow.
Essentially, when a reusable workflow is triggered by a caller workflow, the github context is always associated with the caller workflow. The called workflow is automatically granted access to github.token and secrets.GITHUB_TOKEN 

### Access to reusable workflows:
A reusable workflow can be used by another workflow if:
- Both workflows are in the same repository or
- The called workflow is stored in a public repository, and your organization allows you to use public reusable workflows.


### Runner
A runner is a Server to run the jobs when they’re trigerred. It listens to available jobs and runs only one job at a time. The runners will run the jobs, then report their progress, logs and result back to GitHub. This report can be viewed on the UI of the repository.
A runner is defined using: “runs-on” keyword in a .yml file.
