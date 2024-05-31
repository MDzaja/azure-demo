# Azure Demo
This is a simple demo of how to deploy a simple Azure SQL Server, SQL databases, and a web app using Azure Resource Manager (ARM) [template](./template.json). All resources are deployed to a single resource group.

There is also a [CreateWebApp.ps1](./CreateWebApp.ps1) PowerShell script that can be used to create a new web app in existing resource group and App Service Plan.

## Prerequisites
- Azure CLI
- Azure subscription
- Azure resource group

## Deployment
To deploy the resources, run the following commands in the Azure CLI. Replace `Your-Subscription-ID`, `YourResourceGroup` and `YourSecurePassword` with your own values. The password must be at least 8 characters long and contain at least one uppercase letter, one lowercase letter, and one number.

```bash
az login
az account set --subscription "Your-Subscription-ID"
az deployment group create --resource-group YourResourceGroup --template-file template.json --parameters sqlServerPassword=YourSecurePassword
```

Optional parameters are:
- `sites_demo_web_app_1_name`: The name of the first web app. Default is `demo-web-app-11`.
- `sites_demo_web_app_2_name`: The name of the second web app. Default is `demo-web-app-12`.
- `sites_demo_web_app_3_name`: The name of the third web app. Default is `demo-web-app-13`.
- `sites_demo_web_app_4_name`: The name of the fourth web app. Default is `demo-web-app-14`.
- `servers_demo_test_db_server_name`: The name of the SQL Server. Default is `demo-test-db-server`.
- `serverfarms_demo_shared_web_app_plan_name`: The name of the App Service Plan. Default is `demo-shared-web-app-plan`.
- `sqlServerAdminLogin`: The SQL Server admin username. Default is `sqlAdmin`.
- `demo_database_1_name`: The name of the first SQL database. Default is `demo-db-1`.
- `demo_database_2_name`: The name of the second SQL database. Default is `demo-db-2`.
- `demo_database_3_name`: The name of the third SQL database. Default is `demo-db-3`.


