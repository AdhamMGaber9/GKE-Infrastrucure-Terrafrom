# GKE-Infrastrucure-Terrafrom

## Requirements

### System

- GNU/Linux
- `terraform`
- `docker`
- `kubernetes`

### Get the Code
```
https://github.com/AdhamMGaber9/GKE-Infrastrucure-Terraform.git
cd GCP-DevOps
```
### Get to the Infratrcuture Directory
```
cd Terraform-infastructure
terraform init
terraform plan 
terraform apply
```
### Get to the Jenkins directory 
```
cd ../jenkins
```
### Start by applying the yaml files
- Create `namespace` to isolate the components.
- Create `role` to enable the `jenkins pod` to create, list, delete `services and deployments`.
- Create `service account` to be attached in the `deployment`.
- Create `role bind` to bind the `role` with `service account`.
- Create `service loadbalancer` to create loadbalacer with external ip to access the application.
- >Create `deployment` that contains:
    > - Container with `jenkins` image with container port `8080`.
     > - Execute commands to install `docker cli and kubectl` after pod started using `lifecycle`.
    > - Mount volume to use the `Docker` of the node.
    > - Attach the `service account` to make pod create deployments and services in the same cluster
    > - Create the pod with `root` privilege.
