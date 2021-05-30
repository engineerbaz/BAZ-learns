===========================
CLASS 03 
===========================

#!/bin/bash
# Use this for your user data (script without newlines)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service
systemctl enable httpd.service
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
===

-- 
PRINT IP on Webpage
---


1. Install PHP (yum install -y php)
``` yum install -y php ```
2. Create index.php file with data 
```
<!DOCTYPE html>
<html>  
  <body>
    <p><?php echo "hostname is:".gethostname(); ?></p>
  </body>
</html>
```
3. Restart services
`
systemctl restart httpd.service 
`

Source 
https://stackoverflow.com/questions/59668941/get-server-machine-name-in-html-or-javascript

-------------

-- LOAD BALANCER ---

- Classic LB (v1, Old generation) - 2009 - HTTP, HTTPs, HTTP/2, TCP
- Application LB (v2, new generation) - 2016 - HTTP, HTTPs, WebSockets
- Network LB (v2, new generation) - 2017 - TCP, TLS 

------






























