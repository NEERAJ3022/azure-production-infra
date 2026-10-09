# azure-production-infra

## Resource groups

The reusable Azure resource group module is in `modules/resource_group`. The
`environments/pre_prod` and `environments/prod` roots create separate resource
groups named `rg-pre-prod` and `rg-prod` by default.

Edit `terraform.tfvars` in the environment directory to set the Azure region or
resource group name. Authenticate with Azure CLI (`az login`) or configure the
AzureRM provider environment variables.

```powershell
cd environments/pre_prod
terraform init
terraform plan
terraform apply
```

Repeat from `environments/prod` to manage production independently. Each
environment has its own Terraform state in its working directory; configure a
remote backend before team or production use.