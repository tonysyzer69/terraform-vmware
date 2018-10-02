## terraform-vmware

1. [ Summary. ](#desc)
2. [ Prerequisites. ](#pre)
3. [ Terraform Vsphere Authentication. ](#authentication)
4. [ Create VM. ](#create)
5. [ Delete VM. ](#delete)

<a name="desc"></a>
## 1. Summary of files and directories
* generate_vm.sh - bash script convert definition files into Terraform templates.
* Bootstrap - directory with post install script.
* data - directory with server and storage definition file.
* lib - directory with Terraform templates.

<a name="pre"></a>
## 2. Prerequisites
* Install Terraform https://www.terraform.io/downloads.html

<a name="authentication"></a>
## 3. Terraform Vsphere Authentication
- Create Vcenter login file
- vi ~/.fos-vcenter/terraform.tfvars
vsphere_user = "XXXXXXXXXXXXXXXXX"
vsphere_password = "YYYYYYYYYYYYY"
saccount_username="XXXX"
saccount_password="YYYYYYYYYYYYYY"

<a name="create"></a>
## 4.Create VM

create

<a name="delete"></a>
## 5. Delete VM

delete
