# ==== AWS PSEB === 

CLASS # 02

``` ssh -i <path of pem file> ec2-user@<IP> ```

-i = identity </br>
ec2-user = default user created for EC2

### Connect to EC2
- ssh from cmd
- using Putty
- Instant Connect on web Shell

sudo su
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service ( to start the service )
systemctl enable httpd.service  ( service remains during reboot )




--------------------

Lab: EC2 User Data

#!/bin/bash
# Use this for your user data (script without newlines)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service
systemctl enable httpd.service
echo "Hello World from $(hostname -f)" > /var/www/html/index.html


----------------------

## EC2 Instance Types - Launch Types
- On Demand Instance
  - For short workload 
  - PAYG (per second after first minute)
  - Highest cost as no Upfront cost 
- Reserved Instance
  - Minimum for an year.
  - Sub divide in 3 category
    - Standard Reserved instances
      - Reservation can be from 1 to 3 years
      - reserve a specific instance type
      - upto 75% discount
      - recommended for steady applications
    - Convertible reserved instances
      - Can change type
      - upto 54% discount
      - recommended for long workload with flexible instances
    - Scheduled reserved instances
      - launch within time window you reserve 
      - when yor reserve in fraction of time.
- Spot Instance
  - cheap but not reliable as it can be loose. 
- Dedicated Instance
- Dedicated host




===============
1. How to add billing in IAM user
2. Best practices
3. Permission is on group not user
4. 
















