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
$ cat ~/.fos-vcenter/terraform.tfvars  
vsphere_user = "XXXXXXXXXXXXXXXXX"    
vsphere_password = "YYYYYYYYYYYYY"    
saccount_username="XXXX"    
saccount_password="YYYYYYYYYYYYYY"    

<a name="create"></a>
## 4.Create VM
1. Modify servers definition file    
$ vi data/vm_definitions.csv    

  Sample entry to be added:    
  testserver1,172.16.3.47,1,4096,40,24,172.16.3.1,TMPL-win-srv-2012-std-20180421,fos-qnas01-esx-ds01,fos-prod01,VM Network,FOS

2. Run generate_vm.sh script to generate Terraform templates
$ ./generate_vm.sh

2. Run Terraform to validate template
$ cd lib
$ terraform plan -var-file=~/.fos-vcenter/terraform.tfvars

3. Run terraform to apply the changes
$ terraform apply -var-file=~/.fos-vcenter/terraform.tfvars

<a name="delete"></a>
## 5. Delete VM

delete
