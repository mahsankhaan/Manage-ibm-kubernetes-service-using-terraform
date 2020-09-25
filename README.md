# Automate IBM Cloud Kubernetes Service using Terraform

Terraform is an Open Source software that is developed by HashiCorp that build, change, and version infrastructure safely and efficiently. We can use Terraform to automate IBM Cloud resource provisioning, rapidly build complex, multi-tier cloud environments, and enable Infrastructure as Code (IaC).

The Terraform __configuration files__ describe the resources that you need and how you want to configure them. Based on your configuration, Terraform creates an execution __plan__ and describes the actions that need to be executed to get to the required state. You can review the execution plan, change it, or simply execute the plan. When you change your configuration, Terraform can determine what changed and create incremental execution plans that you can apply to your existing IBM Cloud resources


Steps :
1. Install the Terraform CLI
1. Install IBM Cloud Provider plug-in


Step 1 : Install the Terraform CLI 
1. Open the terminal and create a folder __terraform__ and navigate into that folder.

   ``` mkdir terraform && cd terraform ```

1. Extract the Terraform package and copy the binary file into your terraform directory.
1. Point the __$PATH environment__ variable to Terraform binary file.

   ``` export PATH=$PATH:$HOME/terraform ```

1. Run command __terraform__ to verify that the installation is successful
__NOTE:__ Please restart the device if above command is not executed

