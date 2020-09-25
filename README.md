# Automate IBM Cloud Kubernetes Service using Terraform

Terraform is an Open Source software that is developed by HashiCorp that build, change, and version infrastructure safely and efficiently. We can use Terraform to automate IBM Cloud resource provisioning, rapidly build complex, multi-tier cloud environments, and enable Infrastructure as Code (IaC).

The Terraform __configuration files__ describe the resources that you need and how you want to configure them. Based on your configuration, Terraform creates an execution __plan__ and describes the actions that need to be executed to get to the required state. You can review the execution plan, change it, or simply execute the plan. When you change your configuration, Terraform can determine what changed and create incremental execution plans that you can apply to your existing IBM Cloud resources


Steps :
1. Install the Terraform CLI
1. Install IBM Cloud Provider plug-in


## Step 1 : Install the Terraform CLI 
1. Open the terminal and create a folder __terraform__ and navigate into that folder.

   ``` mkdir terraform && cd terraform ```
1. [Download the Terraform CLI version 0.12.x](https://releases.hashicorp.com/terraform/)
1. Extract the Terraform package and copy the binary file into your terraform directory.
1. Point the __$PATH environment__ variable to Terraform binary file.

   ``` export PATH=$PATH:$HOME/terraform ```

1. Run command __terraform__ to verify that the installation is successful
__NOTE:__ Please restart the device if above command is not executed

## Step 2 : Install IBM Cloud Provider plug-in
Terraform uses the IBM Cloud Provider plug-in to securely communicate with the IBM Cloud REST API. To provision and work with IBM Cloud resources,we must install it.

1. [Download the latest version of the IBM Cloud Provider binary package](https://github.com/IBM-Cloud/terraform-provider-ibm/releases)
1. Extract the IBM Cloud Provider package to retrieve the binary file.
1. Create a hidden folder for plug-in

   ``` mkdir $HOME/.terraform.d/plugins ```
   
1. Move the IBM Cloud Provider plug-in into your hidden folder.
   
   ``` mv $HOME/Downloads/terraform-provider-ibm* $HOME/.terraform.d/plugins/ ```

   
## Step 3 : Let's create IBM resources 
1. Create [IBM Cloud API key](https://cloud.ibm.com/docs/account?topic=account-userapikey#create_user_key)
1. Then create a Terraform project directory. The directory will hold all your Terraform configuration files that you create as part of this tutorial. 
1. Now in project directory, create a __terraform.tfvars__ file and add the __IBM Cloud API key__ that you created earlier. The terraform.tfvars file is a Terraform variables file that you store on local machine. When you initialize the Terraform CLI, all variables that are defined in this file are automatically loaded into Terraform and then can be referenced  in every Terraform configuration file in the same project directory
1. In the same project directory, create a __provider.tf__ file and configure IBM as Terraform provider
```bash

variable "ibmcloud_api_key" {}

provider "ibm" {
  ibmcloud_api_key    = var.ibmcloud_api_key
}```
