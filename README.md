# Deploying a web app to an APACHE server

This project makes use of AWS CloudFormation to create an Ubuntu EC2 instance, setup an **APACHE server** and deploy my web app located in my S3 bucket to the APACHE server

![Infrastructure Diagram](https://res.cloudinary.com/valodagreat/image/upload/v1656684916/APACHE_lugwlj.jpg)
## Setting up the Environment

* Set up AWS by running this command
```bash
aws configure
```
This would prompt you to add your **AWS Access Key ID** and **AWS Secret Access Key**, you'll also be prompted to add your **region** and **output format**

* Create an S3 bucket and upload your index.html or build folder to the bucket, then change the name of the bucket in the yaml file to the name of your bucket
![RolePolicy](https://res.cloudinary.com/valodagreat/image/upload/v1656753432/role_policy_cyxnkk.png)
change the **valodagreat** in the Resource part of the policy to the name of your bucket

* Also change the name of the S3 bucket in the USERDATA section of the instance
![S3bucket](https://res.cloudinary.com/valodagreat/image/upload/v1656754050/instance_dngjsi.png)
change the **s3://valodagreat** in the USERDATA to the name of your bucket
* Create the instance and deploy
```bash
# Create all resources using cloudformation
# Edit the AMI and every necessary parameter specific to you
./create.sh myFirstStack valproject.yml valproject.json 
```

* Update the project if need be
```bash
./update.sh myFirstStack valproject.yml valproject.json 
```

* Delete the project to avoid cost when you are done
```bash
./delete.sh myFirstStack
```
