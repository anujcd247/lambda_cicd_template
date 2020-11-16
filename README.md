# template_cicd_for_a_serverless_app_or_lambda_function

This template is used for the demo of CI-CD of a Lambda function.
Lambda functions are simple to configure and get started with many use-cases ranging from simple server scheduling to implementing complex business logic. Various automation related tasks are possible because there are no servers to manage, it's easy to write the code and often forget about a future enhancement or even the code management.

Resources required before proceeding:
1.	S3 Bucket : A S3 Bucket (Must be in the same region where Code Pipeline is being configured, or to highlight that all resources should be in one region). Let's refer to this bucket as Code bucket.
2.	IAM Role : An IAM role, which will be assumed by CloudFormation with Managed policies attached (AWSLambdaFullAccess, IAMFullAccess, AmazonS3ReadOnlyAccess, AWSCloudFormationFullAccess) let's refer to it as CF-Role.
3.	AWS CodeCommit Repository, let’s refer to it as Demo repo


Let's go through the code, there are four sets of files we need for our setup.
1.	Code: Python code which contains the logic we want to run on Lambda function
2.	requirements.txt: If there are python libraries the code is dependent on, we can consider this file and list all the packages in it; else we can ignore this file.
3.	template.yaml: This is SAM (Serverless Application Model) template which will be used by SAM command specified in buildspec.yml file to create final CloudFormation template containing the Lambda function.
4.	buildspec.yml: This file contains commands which will be required later to create the build package that will get deployed on Lambda.


