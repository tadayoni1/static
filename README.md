# static
A static website that is deployed to AWS with a Jenkins pipeline

Jenkins server is configured to check this repo periodically. When it detects changes it runs the pipeline.
The pipeline that is defined in `Jenkinsfile` includes a step to lint the HTML and then antoher step to upload the html to S3.


### Requirements
* Jenkins
* AWS account
  * S3 bucket
  
Jenkins must be integrated with the github repo.
An S3 bucket must be created in AWS and the name of the bucket must be put into Jenkinsfile. The S3 bucket can be configured for static web hosting.
