## Task 2: Terraform Installation and Nginx Deployment
Terraform is an open-source infrastructure as code software tool. 
Infrastructure as Code (IaC) tools allow users to manage infrastructure with simple declarative language.
Terraform manages external resources such as cloud infrastructure, network appliances, 
software as a service.

### Version of Terraform Installed: v1.9.6
![img.png](data/5_img_9.png)
### Installation
```sudo apt-get update && sudo apt-get install -y gnupg software-properties-common```

```shell
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```

```shell
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```
Output:

![img_6.png](data/5_img_6.png)
etc.

```shell
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

```
Output:

![img_7.png](data/5_img_7.png)

```shell
sudo apt update
```
```shell
sudo apt-get install terraform
```

Terraform installation successfully completed:

![img_8.png](data/5_img_8.png)

Additionally, I have enabled autocomplete for Terraform:

```shell
touch ~/.bashrc
terraform -install-autocomplete
```

### Initialization and application of Terraform configuration

#### Build
```shell
mkdir lab5
cd lab5
```
After that I have added a main.tf with Nginx deployment configuration and executed the following commands:

```shell
terraform init
```
![img.png](data/5_img_10.png)

```shell
terraform apply
```

![img.png](data/5_img_11.png)

![img_1.png](data/5_img_12.png)

Now, we can check the Nginx container running on the specified port:
![img.png](data/5_img_13.png)

And in browser:
![img.png](data/5_img_14.png)

#### Change configuration
To apply changes: firstly, modify the main.tf file (I have changed the external port, then execute the following commands:
```shell
terraform apply
```
![img.png](data/5_img_16.png)

#### Destroy infrastructure
To destroy the infrastructure, I have executed the following command:
```shell
terraform destroy
```

![img.png](data/5_img_15.png)


#### Define variables
I have added a variable.tf file with a variable for container name and added to the main.tf a line "name  = var.container_name".

Now:
```shell
terraform apply
```
![img.png](data/5_img_17.png)

and with defining a custom container name:
```shell
terraform apply -var "container_name=YetAnotherName"
```

![img.png](data/5_img_18.png)


#### Define outputs
After defining ouputs.tf file, after terraform apply command, we can see the output of the container name:
```shell
terraform apply
```

![img.png](data/5_img_19.png)

Also, we can see the outputs of applied changes:
```shell
terraform output
```

![img.png](data/5_img_20.png)

No big problems were encountered during the installation and deployment process. The whole process went smoothly.