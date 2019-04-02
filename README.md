# cloudfront-sg-ip-update
This repository will help you to update Cloudfront and WAF ip address into security group

**** How to use ****

Step - 1 Ready Lambda code with s3 bucket. Bu default i put ireland region. 
	--> If you are working with Other region. Create one s3 bucket and upload code.zip file and make it public accesible.

Step - 2 Execute template cloudfront-ip-update.yml and fill parameters. VPC, S3 bucket and object name. 
	--> This cloudformation will create 4 security group. 2 for https(global and Region) and 2 for http(global and region), lambda function, IAM role for lambda
	
Step - 3 change your region to N.Virginia(us-east-1) and update sns subcription with following steps and detail.
	--> go to sns service (N.virginia region only) --> Subcription --> Create --> Topic Arn - arn:aws:sns:us-east-1:806199016981:AmazonIpSpaceChanged --> Protocol - AWS Lambda --> Paste Endpoint of Lambda function created by template --> Create
	
Hint :- you can find lambda fucntion arn in from cloudformation stack output section. 
