Assignment 1
This assignment is to create an Amazon CloudFront(CDN) for your static content website which you have to host on S3 bucket with domain name (https://devopschallenge.abctest.in)

Case A. If the user opens (https://devopschallenge.abctest.in) it should be seen "Hello, CDN origin is working fine"

  A.1 Create SSL in AWS(Certificate Manager) for the domain name with DNS verification and provide us CNAME record for validation
  A.2 This behavior object content stays in an Edge Cache at for at least 48 hours 
Case B. If user opens (https://devopschallenge.abctest.in/devops-folder/) it should fetch from other S3 bucket and user should see "Hello, CDN 2 origin is working fine"

  B.1 This behavior header should base caching on HOST and CloudFront-Viewer-Country
  
  #..................
  #
  
It seems there is an issue with AWS while working on a task I got stuck in the middle as, Certificate verification on aws is still in pending state from more than 12 hours. PFA for screenshot.
I know the whole task how to perform and implement but due unseen circumstances on AWS I'm not able to proceed further.
  
# Step 1: Transfer Domain to AWS / Route53
# Step 2: Create Custom Domain SSL Certificates
# Step 3: Setup your S3 Bucket Content
# Step 4: Create CloudFront Distributions

# i got stuck on Certificate Manager:
# Verify can be done with CNAME Value : _4fc20d149da2cf066b50f8e299ce05fd.nfyddsqlcy.acm-validations.aws.

 # also i tested with FQDN : https://s3.us-east-2.amazonaws.com/devopschallenge.abctest1.in/Test1.html working fine. but due to certificate verification still pending im not able to proceed for further steps.
  

# Assignment 2
We want to gather some basic statistics for our security team. They want to know the top 8 IP addresses that hit our web servers.

Your task will be the following: Implement a script (use any language you want) to get the top 8 IP addresses out of an existing log file Save your script with no file extension It has to be an executable file there is no need for using arguments The output format will be the following:(8 lines - top saw IP addresses by the number of hits):

<ip_address><number_of_hits>

A real example output would look like this:

$ count

92.6.41.236 22

186.248.72.9 19

81.243.137.36 18

217.118.78.16 15

213.118.39.51 15

93.146.139.64 14

80.116.15.0 14

186.213.159.176 11

Logfile: Click here


# Please find the command to get the task done without using any argument.

cat /var/logfile/access.log | grep http://* | awk '{print $1}' | sort -n | uniq -c | sort -nr | head -n 8
