# aws-lamp
How To Deploy A LAMP Stack In AWS Using Terraform


What is a LAMP stack?

A LAMP stack is simply a web application created on Linux server using Apache, PHP and MySQL (L=Linux, A=Apache, M=MySQL, P=PHP). In this demo, we will use an EC2 Linux instance to create our frontend web application and will use AWS MySQL RDS as backend database.

This demo is configured with AWS Sydney region = ap-southeast-2

You should have your AWS account with Access-key and Secret-Key with Administrative priviliges. You will be asked to enter them as Enviornmental Variables after running "terraform plan" or "terraform apply"

You can put the region name as varibale in Vars.tf by uncommenting last line. And change to "var.region" in provider.tf

Once terraform apply success without issues, copy the db_server_address and web_server_address from the output.

Connect to EC2 instance (web server)

Edit index.php in EC2 instance (web server)

Change <your_aws_mysql_rds_endpoint> with db_server_address from the output

$link = mysql_connect('<your_aws_mysql_rds_endpoint>', 'myuser', 'mypassword');

Save the file and exit

Now, ssh to the ec2 instance of the webserver

Connect to rds instance via ec2

mysql -h <db_server_address> -P 3306 -u myuser -p
#create table and insert data
USE mydb;
CREATE TABLE counter (visits int(10) NOT NULL);
INSERT INTO counter(visits) values(1);

Open web_server_address in the browser , hit refresh and check

LAMP stack successfully deployed in AWS using terraform.

Note: You may need to restart your web server.

Do not forget to destroy LAMP stack using: terraform destroy




