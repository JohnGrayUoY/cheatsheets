# AWS CDK Cheatsheet

https://aws.amazon.com/cdk/

https://docs.aws.amazon.com/cdk/api/v2/

*Written using AWS CDK Version 2.44.0*

---

**cdk init app --language typescript**

* Initialises a new CDK application using Typescript as the specified language.

**cdk synth**

* Generates an AWS CloudFormation template representing the content of the CDK application being built.

**cdk bootstrap**

* Creates a CloudFormation stack named CDKToolkit which is used as a staging area to deploy further CloudFormation stacks.

**cdk deploy**

* Deploys a CloudFormation stack representing the stack specified by the CDK application being built.

**cdk deploy --all**

* Deploys all CloudFormation stacks specified in the CDK application.

**cdk deploy [stack name]**

* Deploys the CloudFormation stack with the specified name from within the CDK application.

**cdk list**

* Lists the names of the current CloudFormation stacks on the users AWS account.

**cdk diff**

* Compares the content of the local CDK templates to the CloudFormation stacks which currently exist on the users AWS account. 

*Note: To use cdk diff, ensure that cdk synth has been called prior to cdk diff, ensuring that the templates on the local machine have been regenerated and represent any changes which have been made locally.*

**cdk destroy <stack name>**

* Destroy the CloudFormation stack with the specified name on the users AWS account. 

*Note: This will only succeed if all resources within the stack are in a state which allows them to be deleted, for example, an S3 bucket can only be deleted if it has no content within it. If a stack contains an S3 bucket which has content within it, then the cdk destroy command will fail.*

**cdk doctor**

* Checks the current CloudFormation stacks on the users AWS account for any potential problems.
