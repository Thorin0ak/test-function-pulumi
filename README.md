# test-function-pulumi
Sample repository to deploy an Azure Durable Function with Pulumi

## Objectives
* Work without VS Code -- WebStorm only
* Create a Pulumi project/Stack
* Create an Azure TypeScript Durable Function using cmd line -- Azure Core Tools
* Deploy using Pulumi

## Getting Started
### Pulumi Initial Setup
```bash
pulumi new azure-typescript
```
Install dependencies, based on [sample repo](https://github.com/pulumi/examples/tree/ca40203279f393c0c159dadcadc97c6007122997/classic-azure-ts-aks-keda):
```bash
npm install @pulumi/azure
npm install @pulumi/azuread
npm install @pulumi/docker
npm install @pulumi/kubernetes
npm install @pulumi/random
npm install @pulumi/tls
```
Used code sample from [this more recent repo](https://github.com/pulumi/examples/tree/master/azure-ts-aks).



### Troubleshooting Issues
## Error creating ServicePrincipal
```text
 Could not create service principal: ServicePrincipalsClient.BaseClient.Post(): unexpected status 403 with OData error: Authorization_RequestDenied: When using this permission, the backing application of the service principal being created must in the local tenant
```
After some investigation, it is because the user does not own the registered application (aks) in Azure AD. The error is reproducible in the Azure Portal FYI.
