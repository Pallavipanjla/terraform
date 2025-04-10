# Terraform + Docker

This project demonstrates how to use Terraform to manage Docker containers — specifically, to pull and run the NGINX web server in a Docker container on your local machine.

---

## Objective

To provision a lightweight, containerized NGINX server using Terraform on your local machine. By the end of this guide, you’ll have:
- A running NGINX Docker container
- A reproducible Terraform configuration
- Full Terraform logs saved to a `.txt` file

---

##  Tools Used

| Tool        | Version   | Purpose                            |
|-------------|-----------|------------------------------------|
| Terraform   | 1.x       | Automate Docker provisioning       |
| Docker      | Latest    | Run containers locally             |
| PowerShell  | Windows   | Command execution                  |

---

##  Prerequisites & Installation

###  Terraform

1. Download from: https://developer.hashicorp.com/terraform/downloads  
2. Extract the zip
3. Option A: Add the folder to `System PATH`  
4. Option B: Use full path to run (e.g., `C:\Terraform\terraform.exe`)

### Docker

1. Download and install: https://www.docker.com/products/docker-desktop  
2. Make sure Docker Desktop is running

---

## How to Deploy NGINX Locally

### Navigate to the Project Folder

```powershell
cd C:\Users\Pallavi\terraform-docker-demo
```

---

### Initialize Terraform

```powershell
C:\Terraform\terraform.exe init
```

 Output should include:  
`Terraform has been successfully initialized!`

---

### Review the Execution Plan

```powershell
C:\Terraform\terraform.exe plan
```
 Output should include:  
`Plan: 1 to add, 0 to change, 1 to destroy.`

---

###  Apply the Configuration

```powershell
C:\Terraform\terraform.exe apply
```

 When prompted:
```
Do you want to perform these actions?
Enter a value: yes
```

 Output should include:  
`Apply complete! Resources: 1 added, 0 changed, 1 destroyed.`

---

### Verify the Docker Container

```powershell
docker ps
```

 You should see:
```
PORTS                  NAMES
0.0.0.0:8081->80/tcp   nginx-server
```

---

### Open in Browser

Go to:

```
http://localhost:8081
```

You should see the default Welcome to NGINX page 

---

## execution_logs.txt

Create a text file named `execution_logs.txt` and paste the full output from the following commands in order:

1. `terraform init`
2. `terraform plan`
3. `terraform apply`
4. `docker ps`

---

## Clean Up (Destroy)

```powershell
C:\Terraform\terraform.exe destroy
```

 When prompted, type: `yes`  
 Output: `Destroy complete! Resources: 1 destroyed.`

---
