
# CloudFormation Task

This project makes use of AWS CloudFormation to create an Ubuntu EC2 instance, setup an **APACHE server** and deploy my web app located in my S3 bucket to the APACHE server

![Infrastructure Diagram](https://res.cloudinary.com/valodagreat/image/upload/v1656684916/APACHE_lugwlj.jpg)
## Setting up the Environment

* Set up AWS by running this command
```bash
aws configure
```
This would prompt you to add your **AWS Access Key ID** and **AWS Secret Access Key**, you'll also be prompted to add your **region** and **output format**

* Create the project and deploy
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
