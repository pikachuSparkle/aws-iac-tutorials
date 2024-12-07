## References:
https://www.youtube.com/watch?v=SLB_c_ayRMo

## Create EC2 instances

main.tf
```
# https://registry.terraform.io/providers/hashicorp/aws/latest/docs
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

# Configure the AWS Provider
provider "aws" {
  region     = "us-east-1"
  access_key = "YYYYYYYYYYYYYYYYYYYYY"
  secret_key = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
}

# Create a EC2 instance
# https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance
resource "aws_instance" "my-first-server" {
  ami           = "ami-0a0e5d9c7acc336f1"
  instance_type = "t2.micro"

  tags = {
    Name = "tag-my-first-server"
  }
}

```