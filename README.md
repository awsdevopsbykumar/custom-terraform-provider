# Terraform Provider CMDB

This folder encapsulates the Terraform Provider that issues API calls to the CMDB microservice.

## Disclaimer

This project is meant to be for demonstration purposes only. There are many things that should be improved upon within
the code before this project would be considered production ready. 

## Running the cmdb app
To run the CMDB app need to perform following steps
Step 1: cd into /opt/custom-terraform-provider/cmdb considering you have clone code into this directory
```
cd /opt/custom-terraform-provider/cmdb
go run main.go
```
Output will be look like below
2021/08/07 18:43:01 Booting up server v1 on 8990

## Running the example

To run the Terraform Provider locally there are a few steps to complete:

Step 1: Change the directory where you have clone the code and build the source code locally

```
cd /opt/custom-terraform-provider/terraform-provider-cmdb
go build -o terraform-provider-cmdb_v1.0.0
```

Step 2: Create a directory and move the executable into the local terraform plugin folder:

```
mkdir -p terraform.d/plugins/linux_amd64/
mv terraform-provider-cmdb_v1.0.0 terraform.d/plugins/linux_amd64/
```

Step 3: From within this directory, initialize Terraform:

```
terraform init
```

Step 4: Run an apply via Terraform:

```
terraform apply
```

The output generated should look similar to the following:

```
Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

Outputs:

vm_1_details_raw = {"Name":"M2540TCOLRus","Type":"COL","Region":"us-east-1"}
vm_1_name = M2540TCOLRus
vm_1_type = COL
```
