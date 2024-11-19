
# Secure File Upload Workflow with Azure Static Web Apps, SAS Tokens, and Blob Storage

This repository demonstrates the creation of a secure file upload workflow using Azure Static Web Apps, Azure Blob Storage, and Shared Access Signatures (SAS) tokens. This approach provides a secure, scalable solution for file uploads and storage in Azure.

For a more detailed explanation of how this project was developed and deployed, you can refer to my [Medium blog post](https://medium.com/@venkatnarayanakuruva/building-secure-file-upload-workflows-with-static-web-apps-sas-tokens-and-azure-blob-storage-dbb4256bf56d).

## Project Overview

The project consists of:
- **Frontend**: A React app built with Vite that interacts with the backend and allows users to upload files securely.
- **Backend**: Azure Functions (Node.js) that generate SAS tokens and handle the file upload requests.
- **Security**: The solution uses SAS tokens to allow temporary access to Azure Blob Storage, ensuring files are securely uploaded without exposing sensitive credentials.

## Features

- **Frontend**: Simple React 18 app built using Vite with a focus on user authentication and file upload functionality.
- **Backend**: Azure Functions (v4, Node.js) that dynamically generate SAS tokens for secure file uploads.
- **Blob Storage Integration**: Uploads files to Azure Blob Storage with the generated SAS token.
- **Dev Environment**: Easy setup using [SWA CLI](https://learn.microsoft.com/en-us/azure/static-web-apps/static-web-apps-cli-configuration) for local development.

## Repository Structure

| Folder/Name       | Description                                            |
|-------------------|--------------------------------------------------------|
| `.devcontainer`   | Local development configuration for Azure Static Web Apps CLI (SWA CLI). |
| `app-react-vite`  | Frontend app using React 18 and Vite with authentication and file upload functionality. |
| `api`             | Backend Node.js Azure Functions with `/status` and SAS token generation routes. |
| `docs`            | Documentation and setup resources for configuring and deploying the app. |
| `example-workflows` | Example GitHub Actions workflows for CI/CD pipeline. |

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (LTS version recommended)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/)
- [Azure Functions Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local)
- [SWA CLI](https://learn.microsoft.com/en-us/azure/static-web-apps/static-web-apps-cli-configuration)

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. Install dependencies for the frontend:
   ```bash
   cd app-react-vite
   npm install
   ```

3. Install dependencies for the backend:
   ```bash
   cd ../api
   npm install
   ```

4. To start local development, use the SWA CLI to proxy the frontend and backend:
   ```bash
   swa start
   ```

5. The frontend app will be available at `http://localhost:3000` and the backend API at `http://localhost:7071`.

### Deploying to Azure

1. Deploy the app and API to Azure Static Web Apps:
   ```bash
   swa deploy
   ```

2. Ensure Azure Blob Storage is configured and your backend API is generating SAS tokens as described in the [Medium blog](https://medium.com/@venkatnarayanakuruva/building-secure-file-upload-workflows-with-static-web-apps-sas-tokens-and-azure-blob-storage-dbb4256bf56d).

### File Upload Process

- **Frontend**: The user selects a file, which triggers an API request to generate a SAS token.
- **Backend**: The Azure Function generates a SAS token and returns it to the frontend.
- **Blob Storage**: The file is uploaded directly to Azure Blob Storage using the SAS token.

## Documentation

- **Frontend**: React 18 (Vite) app for file upload.
- **Backend**: Node.js Azure Functions for generating SAS tokens and file upload handling.
- **CI/CD**: GitHub Actions workflow examples for automatic deployment.

## License

This project is licensed under the MIT License. See the LICENSE file for more information.

## References

- [Medium Blog: Building Secure File Upload Workflows](https://medium.com/@venkatnarayanakuruva/building-secure-file-upload-workflows-with-static-web-apps-sas-tokens-and-azure-blob-storage-dbb4256bf56d)

