# azure-blob-demo

A simple demo that uses the Azure Blob Storage client library.

## Setup

Perform the following actions to prepare Azure, and your local environment, for the exercise.

1. Sign in to Azure by using the following command. A browser window should open letting you choose which account to sign in with.

    ```bash
    az login
    ```

1. Create a resource group for the resources needed for this exercise. Replace `<myLocation>` with a region near you (e.g `westeurope`).

    ```bash
    az group create --location <myLocation> --name azure-blob-demo-rg
    ```

1. Create a storage account. Create a storage account to use in the application. Replace `<myLocation>` with the same region you used for the resource group. Replace `<myStorageAccount>` with a unique name.

    ```bash
    az storage account create --resource-group azure-blob-demo-rg --name <myStorageAccount> --location <myLocation> --sku Standard_LRS
    ```

1. Get credentials for the storage account.

    * Navigate to the Azure portal.
    * Locate the storage account created.
    * Select **Access Keys** in the **Security + Networking** section of the navigation pane. Here, you can view your account access keys and the complete connection string for each key.
    * Find the Connection string value under key1, and select the Copy button to copy the connection string.
    * Set `AZURE_BLOB_CONNECTION`:

      ```bash
      export AZURE_BLOB_CONNECTION="<myConnectionString>"
      ```

## Run

It's time to build and run it:

```bash
dotnet build
dotnet run
```

## CleanUp

The app deleted the resources it created. You can delete all of the resources created for this demo by using the following command. You need to confirm that you want to delete the resources.

```bash
az group delete --name azure-blob-demo-rg --no-wait
```

## License


This project is licensed under the [MIT License](LICENSE).
