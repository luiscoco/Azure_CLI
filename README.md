# Azure CLI

## 1. How to Install Azure CLI

To **Install Azure CLI** follow the instructions in this web page:

https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows (English version)

https://learn.microsoft.com/es-es/cli/azure/install-azure-cli-windows (Spanish version)

Open a **PowerShell** Window as Administrator:

<img width="968" height="330" alt="image" src="https://github.com/user-attachments/assets/a30634a3-1430-447c-aa44-53bfafa5f93f" />

Then we execute this command to **Install Azure CLI**:

```
winget install --id Microsoft.AzureCLI
```

<img width="999" height="303" alt="image" src="https://github.com/user-attachments/assets/2635cfea-c6ff-4a47-991b-d367f3ee301f" />

## 2. How to UnInstall Azure CLI

If you prefer to **Uninstall** a previous **Azure CLI** version, please run this command:

```
winget uninstall --id Microsoft.AzureCLI
```

<img width="620" height="105" alt="image" src="https://github.com/user-attachments/assets/89f4ff84-8f36-4b9b-9add-b2a30100bcd7" />

## 3. How to Check Azure CLI version installed 

After installing Azure CLI run this command to validate the installation and view the version

```
az --version
```

<img width="992" height="463" alt="image" src="https://github.com/user-attachments/assets/9b729d58-3d7b-4c06-8409-2b19a126630a" />

## 4. Basic and Most Commonly Used Azure CLI Commands

Here are the basic and most commonly used Azure CLI commands to get started with managing your Azure resources from the terminal:

### 4.1. Authentication and Account Commands

Login to Azure:

```bash
az login
```

Opens a browser window to log in with your Azure credentials.

Show current account details:

```bash
az account show
```

List all subscriptions:

```bash
az account list --output table
```

Set a specific subscription to work with:

```bash
az account set --subscription "<subscription-name-or-id>"
```

### 4.2. Resource Groups Commands

List all resource groups:

```bash
az group list --output table
```

Create a resource group:

```bash
az group create --name MyResourceGroup --location eastus
```

Delete a resource group:

```bash
az group delete --name MyResourceGroup
```

### 4.3. Virtual Machines Commands

List all VMs:

```bash
az vm list --output table
```

Start a VM:

```bash
az vm start --resource-group MyResourceGroup --name MyVM
```

Stop (deallocate) a VM:

```bash
az vm deallocate --resource-group MyResourceGroup --name MyVM
```

Restart a VM:

```bash
az vm restart --resource-group MyResourceGroup --name MyVM
```

### 4.4. Storage Accounts Commands

List storage accounts:

```bash
az storage account list --output table
```

Create a storage account:

```bash
az storage account create --name mystorageaccount --resource-group MyResourceGroup --location eastus --sku Standard_LRS
```

### 4.4. App Services 
🔹 List app services:
bash
Copiar
Editar
az webapp list --output table
🔹 Create a web app:
bash
Copiar
Editar
az webapp create --resource-group MyResourceGroup --plan MyAppServicePlan --name MyUniqueAppName --runtime "DOTNET|6.0"
🔐 Azure Key Vault
🔹 List all key vaults:
bash
Copiar
Editar
az keyvault list --output table
🔹 Get a secret from Key Vault:
bash
Copiar
Editar
az keyvault secret show --vault-name MyVault --name MySecret
📋 General Notes
Add --output table, --output json, or --output yaml to control output formatting.

Use az find "<command>" to discover examples, e.g.:

bash
Copiar
Editar
az find "az vm"
