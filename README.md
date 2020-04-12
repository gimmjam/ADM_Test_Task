# ADM_Test_Task
Task for DevOps position

This is to set up wordpress using AWS infrastructure. I have used terraform to provision infrastructure. Code uses and creates following AWS services.

1. VPC and it's components
2. Subnets, Route Tables, Internet Gateway, Nat Gateway.
3. EC2 instance
4. EIP for NAT Gateway
5. RDS mysql instance. ( I tried to create seperate AWS instance for DB, but it didn't worked :( )
6. Security Groups to access both EC2 and MYSQL


### Pre-requisites:
 
1. You need to have Ssh keys generated and should be put into `~/.ssh/` , if your machine is windows then feel free to use diff path and update the same in the `ssh_key` variable in the `vars.tf`

2. Create an IAM user and create security credentials(AccessKey, SecretKey) and update in the `~/.aws/credentials` file like below
   ![terraform-aws-profile]
   
3. IAM User Policy Used : AdministratorAccess
   
4. Region : Europe (London) eu-west-2
   
 Note : if you have default profile, just erase the `profile` attribute in `provider.tf`
 
   
### Install Terraform on Centos 7 or Redhat linux

sudo yum update -y
yum install wget unzip -y
sudo wget https://releases.hashicorp.com/terraform/0.12.24/terraform_0.12.24_linux_amd64.zip
sudo unzip terraform_0.12.24_linux_amd64.zip
sudo mv terraform /usr/local/bin/
 Terraform v0.12.24

### Provisioning:

1. git clone - https://github.com/gimmjam/ADM_Test_Task.git
2. cd terraform-aws-wordpress
2. terraform init
3. terraform plan
4. terraform apply -auto-approve


### Destroying the Infra:
1. cd terraform-aws-wordpress (Be in the repo directory)
2. terraform destroy -auto-approve


