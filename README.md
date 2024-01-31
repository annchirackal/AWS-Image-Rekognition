# Image Recognition using AWS Image Rekognition
An app for image recognize images of different cars using AWS Image Rekognition. 
## Objectives :
This is an academic project. The aim of the project is to build a distributed system to develope a Parallel Machine Learning (ML) model utilizing an open dataset(given)
, deploy it in AWS Elastic Container Registry (ECR), and train the model concurrently across 2 EC2 instances.


## Features:
- two instances work will in parallel: for example, instance A is processing image
3, while instance B is processing image 1 that was recognized as a car by instance A.
When instance A terminates its image processing, it adds index -1 to the queue to signal
to instance B that no more indexes will come.
## Prerequisites/Steps For Execution:
This project is done using Eclipse IDE with java version Java 17 (OpenJDK 17).
You can use any IDE and any java version. Make sure that you use the same version of
the java as of your local system in your EC2 instance also.
- Part 1: Java code in local system:
1. Install AWS tool kit from IDE and create a new project under aws toolkit for eclipse.
2.  Create a new class under com.amazon.samples.
  ![image](https://github.com/annchirackal/AWS-Image-Rekognition/assets/52249835/b752a43b-e780-4c0f-a9ba-291d66efe064)
3. clone the forked repo.
  - update credentials and configuration file in .aws folder .(C/users/your user/.aws) aws_access_key_id and aws_secret_access_key can be copied from AWS lab
4.  Execute and test your code
5.  Build the jar file.
  ![image](https://github.com/annchirackal/AWS-Image-Rekognition/assets/52249835/23750093-ed67-4cd9-b6a0-414229fa8541)
  - Part 2. EC2 instance.
1. Create two ec2 instances with aws linux machine and stall both java and maven in ec2
instance. Make sure java version same as that of your java version in local.
Refer below links for steps:
https://techviewleo.com/install-java-openjdk-on-amazon-linux-system/
https://softchief.com/2017/11/07/installing-maven-using-yum-on-ec2-instanceamazon-linux/
2. Upload your instance Ec2
Run below command in command terminal of local system.(change your .pem file path,
.jar file path and ec2 instance public key accordingly)
$ scp -i /Users/Ann/file.pem /Users/Ann/cs643-0.0.1-SNAPSHOT.jar ec2-user@ec2-54-
167-73-176.compute-1.amazonaws.com:~
3.Connect to ec2 instance.
$ ssh -i "file.pem" ec2-user@ec2-44-202-85-30.compute-1.amazonaws.com
(update the location of .pem file and Public DNS)
4. Setup config file with vommand $ .aws configure
Paste your aws_access_key_id and ‘enter key’
Same was paste the aws_secret_access_key and region. Out file format is text
5.set up aws credentials in ec2 instance using below command(this is required only if
you are using and educational account. Otherwise you can setup an IAM role).
sudo nano ~/.aws/credentials
opy and paste aws crendiatls including token.
(clt+O, enter, clt+X)
6.Run your code in VM using $ java -jar your jar file name.jar

## Technologies Used
- Java
- Spark
- AWS



