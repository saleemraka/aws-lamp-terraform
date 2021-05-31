# aws-lamp
How To Deploy A LAMP Stack In AWS Using Terraform


What is a LAMP stack?

A LAMP stack is simply a web application created on Linux server using Apache, PHP and MySQL (L=Linux, A=Apache, M=MySQL, P=PHP). In this demo, we will use an EC2 Linux instance to create our frontend web application and will use AWS MySQL RDS as backend database.

This demo is configured with AWS Sydney region = ap-southeast-2

You should have your AWS account with Access-key and Secret-Key with Administrative priviliges. You will be asked to enter them as Enviornmental Variables after running "terraform plan" or "terraform apply"

You can put the region name as varibale in Vars.tf by uncommenting last line. And change to "var.region" in provider.tf

Once terraform apply success without issues, copy the db_server_address and web_server_address from the output.



