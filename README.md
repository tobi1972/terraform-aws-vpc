# terraform-iaac-august-2020

```
module "VPC" {
  source              = "../"
  region              = "us-east-1"
  cidr_block          = "10.0.0.0/16"
  private_cidr_block1 = "10.0.1.0/24"
  private_cidr_block2 = "10.0.2.0/24"
  private_cidr_block3 = "10.0.3.0/24"
  public_cidr_block1  = "10.0.101.0/24"
  public_cidr_block2  = "10.0.102.0/24"
  public_cidr_block3  = "10.0.103.0/24"
  instance_type       = "t2.micro"
  instance_class      = "db.t2.small"
  multi_az            = "true"
  username            = "rootuser"             #Database username
  name                = "admin"                #Database name
  password            = "oshikoya"             #Database password
  engine              = "mysql"
  engine_version      = "5.7"
  db_p_name1          = "rds-pg"
  db_p_name2          = "character_set_server"
  db_p_name3          = "character_set_client"
  allocated_storage   = 20

  tags = {
    Name        = "VPC_Project"
    Environment = "Dev"
    Department  = "IT"
    Team        = "Infrastructure"
    Created-by  = "John Oshikoya"
  }

  tags2 = {
    Name = "wordpress"
  }

  tags3 = {
    Name = "db"
  }
}
```

### Get the output

```
output "vpc_id" {
  value = "${module.VPC.vpc_id}"
}

output "private_subnet1" {
  value = "${module.VPC.private_subnet1}"
}

output "private_subnet2" {
  value = "${module.VPC.private_subnet2}"
}

output "private_subnet3" {
  value = "${module.VPC.private_subnet3}"
}

output "public_subnet1" {
  value = "${module.VPC.private_subnet1}"
}

output "public_subnet2" {
  value = "${module.VPC.private_subnet2}"
}

output "public_subnet3" {
  value = "${module.VPC.private_subnet3}"
}

output "tags" {
  value = "${module.VPC.tags}"
}

output "tags2" {
  value = "${module.VPC.tags2}"
}

output "tags3" {
  value = "${module.VPC.tags3}"
}

output "CENTOS_AMI" {
  value = "${module.VPC.CENTOS_AMI}"
}

output "UBUNTU_AMI" {
  value = "${module.VPC.UBUNTU_AMI}"
}

output "pub_az" {
  value = "${module.VPC.pub_az}"
}

output "priv_az" {
  value = "${module.VPC.priv_az}"
}

```