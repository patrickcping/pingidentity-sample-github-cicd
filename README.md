# Sample Github CICD Pipeline - PingFederate / PingAccess

To run:

* Ensure the cluster has a service principal created that has `Contributor` role - see [Azure documentation](https://docs.microsoft.com/en-us/azure/dev-spaces/how-to/github-actions)
* Clone the repo, make sure Github actions are enabled
* Adjust the [helm values](./helm-values) files for PingFederate and PingAccess to align with your environment
* Set the project secrets (see table below)
* Commit changes and observe GitHub action pipeline output

## Project Secrets

Set the following secrets in your repository:

| Secret Name | Purpose |
|--|--|
| AZURE_CREDENTIALS | The full JSON output from `az ad sp create-for-rbac --sdk-auth --skip-assignment` command |
| CLUSTER_NAME | The AKS cluster name in Azure |
| MASTER_SPACE | The namespace in the AKS cluster to deploy the software to |
| RESOURCE_GROUP | The Azure resource group that contains the AKS cluster |
| PINGFEDERATE_LICENSE | The full contents of the pingfederate.lic license file |
| PINGFEDERATE_LICENSE_SECRET_NAME | A name to call the PingFederate license secret in the AKS cluster |
| PINGACCESS_LICENSE | The full contents of the pingaccess.lic license file |
| PINGACCESS_LICENSE_SECRET_NAME | A name to call the PingAccess license secret in the AKS cluster |

