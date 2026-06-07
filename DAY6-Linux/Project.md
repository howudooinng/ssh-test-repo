Day - 8

Project - Write a Script to report the usage of AWS in your Project ?

Problems of having an on-prem infrastructure —> management of the infrastructure, and also save the cost of extra resources which are not being used.

As a DevOps Engineer one of the primary responsibility is to maintain the cost effectiveness of the system.

Example.com —> EC2, S3, Lambda functions, IAM

Goal —> everyday at 6 pm, give this report to a reporting Dashboard

How to do this —> by using Shell script, which will have all the information in a file for all the resources which are being used within example.com company.

Shell script can be paired with Cron Job at a particular given time and get the script executed

get the aws cli and also connect ec2 to the aws account using aws configure 



