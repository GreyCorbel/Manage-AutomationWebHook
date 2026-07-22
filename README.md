# Manage-AutomationWebHook GitHub Action

The Manage-AutomationWebHook action provides a seamless experience for managing Azure Automation Account Webhooks. It automatically updates and links webhooks to your runbooks based on your local project structure.

Integrate this action into your GitHub workflow to fully automate your Webhook deployments! 

## How does it work?

The logic of this action relies on a predefined directory structure, primarily focusing on the `Definitions` folder where your webhook JSON definitions are stored.

### Directory tree example:
` ` `text
-Definitions
    -Webhooks
        -my-webhook.json
-Source
    -Common
` ` `

### Webhook Definition Example
Example of a webhook file named **my-webhook.json**:
` ` `json
{
    "Name": "my-webhook",
    "RunbookName": "test",
    "IsEnabled": true,
    "ExpiryTime": "2026-12-31T00:00:00Z"
}
` ` `

## Action Inputs
* **environmentName** (required) - Defines the environment for which you want to perform synchronization.
* **projectDir** (required) - Defines the path where the predefined directory structure is located.
* **subscription** (required) - Defines the subscription in which Azure Automation resides.
* **azureSubscription** (required) - Defines the Azure credentials.
* **resourceGroup** (required) - Defines the resource group.
* **automationAccount** (required) - The name of the Azure Automation account.
* **verboseLog** - A switch for detailed logging.
