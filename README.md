# Brief overview:

**My-avax-project**: This folder includes file structure of main terraform script which is using GCP as its provider, this is associated with two modules which are named as ‘node’ and ‘vpc’ in different folder.

* The main.tf file would call the existing modules which are briefly described below.
* The variables.tf includes all the variables which are created for use.
* The terraform.tfvars has all the values for the variables to call for, in this same file we have region, zone, project name, etc which are used to get values in the architecture diagram below.
* The backend.tf file is being used to store terraform state file in a GCS storage.

**Modules:**
* _Node_: This module consists of 4 resources, these are for compute_disk, compute_engine, compute_firewall and compute_address. This module also has count as a meta-argument to accept & create as many instances,, external IPs and disks as required.
* _Vpc:_ This module enables API at first using google_project_service resource then it’ll create VPC and subnet using compute_network and compute_subnetwork resources.

The architecture diagram attached below shows the visual representation of above terraform code:

![image](https://github.com/karanchhatwani/avalanche/assets/50554667/66f68d35-b8da-4bfb-8e36-2fa85753d520)
