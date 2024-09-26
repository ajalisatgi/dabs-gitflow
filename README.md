# GitFlow using Databricks Asset Bundles

## Overview

This project can be used to bootstrap Databricks deployments that require implementing a GitFlow branching model. Databricks Asset Bundles (DABs) package the relevant Databricks assets together and deploy them across different workspaces. GitHub Actions workflows automate the constructs as they apply to the GitFlow branching model and invoke DABs for deployments. 

The following image represents the end-to-end implementation of the GitFlow branching model for managing Databricks deployments.
![image](https://github.com/user-attachments/assets/ae25ba29-2bb1-4152-8259-76f4fe1895ae)

    
## Prerequisites
Following are the pre-requisites that are needed to use the code in this repository to manage deployments for your specific Databricks workspaces.
* Clone this repository 
* Provision 3 distinct Databricks workspaces: `DEV`, `QA` & `PROD`
* Create two distinct service principals via the account console for the `QA` and `PROD` Databricks workspaces respectively
* Assign the service principals created in the previous step to the respective `QA` and `PROD` workspaces
* Create an Oauth secret for both Service Principals and make a note of the the `Client ID` and `Secret`  
* Update the `databricks.yml` file in the root of this repository with the following details pertaining to your environment:
  * workspace host for `DEV`, `QA` and `PROD` Databricks workspaces
  * service principal name for `QA` and `PROD` service principals
* Create GitHub environments for `QA` and `PROD`
* Create the following secrets in both `QA` and `PROD` GitHub Environments:
  * `DATABRICKS_HOST_URL`
  * `DATABRICKS_SP_CLIENT_ID`
  * `DATABRICKS_SP_SECRET`
---

## Standard Release Process
The following image represents the steps involved in deploying a Standard Release
![image](https://github.com/user-attachments/assets/e50ef525-60f4-4680-abb2-38ec7ea90e89)


---
## Hotfix Release Process
The following image represents the steps involved in deploying a Hotfix Release
![image](https://github.com/user-attachments/assets/73cbdd53-84b8-43ae-bfb5-2b944a3c7e65)










