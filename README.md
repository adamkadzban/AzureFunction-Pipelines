# AzureFunction-Pipelines

A simple example of a .NET Azure Function that is built and deployed via Azure DevOps Pipelines.

## Description

- ci.yml: Simple build to run on every PR.
- cd.yml: Build and deploy the app.
- swap.yml: Swap slots.

## Builds

There are no build scripts. It might be worth adding them as a POC. Just run ```dotnet build --configuration Release --output ./output``` from the project folder.

## Deployments

Builds on the `main` branch wait for approval to deploy to the stage slot (configured via the Environment). Then, they wait for manual verification before swapping to production.

If the CI pipeline is manually triggered on the `main` branch, then the Release pipeline (configured via UI) is automatically triggered. It deploys to stage, waits for manual approval, then swaps to production.

## Links

- Pipelines: https://dev.azure.com/adamkadzban/AzureFunction-Pipelines/_build
- Production HTTP Trigger: https://azurefunction-pipelines.azurewebsites.net/api/Function1
- Stage HTTP Trigger: https://azurefunction-pipelines-stage.azurewebsites.net/api/Function1
- Azure Function App Task: https://docs.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-function-app?view=azure-devops
- Azure App Service Manage Task: https://docs.microsoft.com/en-us/azure/devops/pipelines/tasks/deploy/azure-app-service-manage?view=azure-devops


Hi Aaron
