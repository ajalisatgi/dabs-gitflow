# GitFlow using Databricks Asset Bundles

## Overview

This project can be used to bootstrap Databricks deployments that require the implementation of a GitFlow branching model. Databricks Asset Bundles (DABs) is used to package the relevant Databricks assets together and deploy accross different workspaces. GitHub Actions workflows are used to automate the constructs as they apply to the GitFlow branching model and invoke DABs for deployments. 

The following image represents the end-to-end implementation of the GitFlow branching model for deploying Databricks deployments.
![](2022-12-21-00-39-09.png)
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
The following image represents the steps involved for deploying a standard Release
![](2022-12-21-00-39-09.png)

---
## Hotfix Release Process
The following image represents the steps involved for deploying a Hotfix Release
![](2022-12-21-00-39-09.png)








