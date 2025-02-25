# How Terraform Work
Infrastructure as Code (IaC)

Directed Acyclic Graph
-It is connected all dotes
- Cant go back 
- Graph can have multiple links

Terraform keeps *state file* (It is a json file)


```terraform
provider "aws" {
    profile = "default"
    region  = "us-west-2"
}

resource "aws_s3_bucket" "tf-course" {
    bucket  = "<name of bucket>"
    acl = "private"
}
```