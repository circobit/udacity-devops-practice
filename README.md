# udacity-devops-practice

This repo contains some DevOps exercises provided by Udacity.

# How to run the Cloudformation commands

In order to facilitate the Cloudformation deployment/update/delete commands, 
I added files:

- cloudformation/0-helpers/create.sh
- cloudformation/0-helpers/update.sh
- cloudformation/0-helpers/delete.sh

Both files are symlinked within the directories that contain the resources 
to provide a faster way to run the deployment commands. 

To deploy a stack, run:

`./create.sh <STACK-NAME> <RESOURCES-FILE> <PARAMETERS-FILE>`

Example:

`./create.sh demo-infra network.yml network-parameters.json`

To update a stack, run:

`./update.sh <STACK-NAME> <RESOURCES-FILE> <PARAMETERS-FILE>`

Example:

`./update.sh demo-infra network.yml network-parameters.json`

To delete a stack, run:

`./delete.sh <STACK-NAME>`

Example:

`./delete.sh demo-infra`