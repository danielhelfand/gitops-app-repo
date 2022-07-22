# gitops-app-repo

This repository contains source code for a sample application to be used 
as part of a walkthrough on using Argo CD for GitOps using two separate 
repositories: an app and deployment repository.

This app repository contains a Java application and CI process that will 
push a container to ghcr.io. Once the container is pushed, you can use 
it to update the deployment repository to deploy any changes to this 
repository to your Kubernetes cluster via Argo CD.

## Prerequisites

You will need a GitHub account to complete this section of the walkthrough.

## Walkthrough

Before going through these instructions, make sure you have completed the 
first section in the [gitops-deployment-repo](https://github.com/danielhelfand/gitops-deployment-repo). 

1. Fork this repo to your GitHub account
2. Under the `Actions` tab for the repo, click that you would like to allow 
GitHub actions to run for this repo
3. Let's make a change to the application by changing the score users get when 
they hit objects in the game from 100 to 10 points. You can do this by editing 
this line in the [code](https://github.com/danielhelfand/gitops-app-repo/blob/b8b96a37d7178d78b72dba18c17b4d9147ab4a16/src/main/resources/static/assets/game.js#L130).
4. Make the change either through the GitHub UI or clone the repo locally
5. After making the change, commit to the master branch of the repository
6. You can view the logs of the CI process through the GitHub UI where you can 
the container being built and pushed to ghcr.io
7. When the CI process finishes, you can return the main link for your forked repo 
and click on `gitops-app-repo` under `Packages`
8. Grab the `Digest` of the container to update the deployment repo
9. Head back to the deployment repo to complete part two of the deployment repo and 
see this change synced out to your Kubernetes cluster
