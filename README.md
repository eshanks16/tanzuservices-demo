# Tanzu Services Demo


## Overview
The items contained within this repository are used for demonstrating Tanzu services in a 
VMware Cloud environment.

Before using this repository, you should already have a VMware Cloud on AWS SDDC setup and
have the Managed Tanzu Kubernetes Grid Service activated. You should also have a namespace
and a Tanzu Kubernetes Cluster deployed and ready to use with the demo.

Each directory starting with a Demo# (eg. `demo1-`) should have instructions for running a
demo on VMware Cloud on AWS with Tanzu services. 


-----
## How to Contribute
  
Please create a PR if you have suggestions on additional demos for the field. 

1. Create a new folder with a new demo number.
2. Create a markdown document named `readme.md` and place your instructions in here.
> Note: If you would like to include pictures in your readme (recommended), place images
in the img folder. You can use demo1's readme as an example.
3. Include any YAML or scripts for the demo within that demo# directory.


All Demos should assume the following were created prior to the demo:
- VMware Cloud on AWS SDDC
- Tanzu Kubernetes Grid Service has been activated
- A vSphere Namespace was created using the `vsan-default-storage-policy`
- The Supervisor cluster was registered with TMC
- A Tanzu Kubernetes cluster (TKC) was created (maybe or maybe not registered in TMC)

