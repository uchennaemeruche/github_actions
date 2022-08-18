# Github Actions

Github Actions helps to automate the build, test and deployment pipeline of a software all within Github. With Github Actions, teams can define highly advanced pipelines.


## Workflows
Workflows refers to an automated procedure that is made up of one or more Jobs which can either run sequentially or in parallel. Workflows can be triggered by events in the repository, triggered manually or scheduled.

 Creating a workflow:
 A  YAML(.yml) file in the .github->workflows folder of our repository defines a workflow. 
A repository can have multiple workflows, each of which can perform different set of tasks. A workflow can be designated to build and test pull requests, and another to deploy  an application everytime a release is created.  
Workflows are reusable in that, they can be accessed from other workflows. Reusing workflows helps to avoid duplication of codes, thus leading to more maintanable codebase.
A workflow that uses another workflow is called a ‘caller’ workflow. The reusable workflow is a ‘called’ workflow.
Actions in a called Workflow reused from a different repository will run as if they were part of the caller workflow.
Essentially, when a reusable workflow is triggered by a caller workflow, the github context is always associated with the caller workflow. The called workflow is automatically granted access to github.token and secrets.GITHUB_TOKEN 