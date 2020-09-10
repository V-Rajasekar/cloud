# Amazon Cloud Formation


# Contents
- [what is CloudFormation ?](#what-is-CloudFormation?) 
- [Four Key Concepts](#four-key-concepts)
- [CloudFormation Designer](#cloudFormation-designer)
- [Getting Started](#getting-started)
- [Best Practices](#best-practices)
- [Resources](#resources)


### what is CloudFormation?
"AWS Cloud formation enables to create and provision AWS infrastructure deployments predictably and repeatedly".

AWS cloud formation is a tool in order to create environment in AWS Cloud from a template.

###  Four key concepts:

1. Template: 
-  A template is a simple text file that describes a stack, a collection of AWS resources you want to deploy together as a group. You use the template to define all the AWS resources you want in your stack. This can include Amazon Elastic Compute Cloud instances, Amazon Relational Database Service DB Instances, and other resources
- The content of the template is JSON or YML
- All cloud services Compute, Storage, Database services can be deploed through the clod formation tool.
- The interaction of cloud formation with these various services is controlled by IAM so no AWS services trusts any other AWS Service.

2. Stack: 
-Stack are simply a collection of resources that are managed as single unit.
-They are created with the template.
-Create, Update, delete stack.
-All of the resource in use by a stack are defined in that template, you submit it to CloudFormation and then CloudFormation is going to instantiate all of these entities  or those resources that you need for this stack to be up and running.
-Manage stack via the console, the API or the CLI.
3. ChangeSet: 
-Is the summary of proposed changes to update the stack.
- I have an example here Our goal is to change the name of an RDS instance. In order for CloudFormation to do this,
 it's going to create a new database and delete the old one. The data in the old database is lost unless its backed up.
 A change set will inform you of this database impact. So change sets are very helpful when it comes to CloudFormation. 
 Here's an example of a change set just so can see how they work. You take your template and you edit it. 
 You have it locally or it's in an S3 bucket, use CloudFormation to generate a change set. So what CloudFormation is going to do 
 is going to compare the current running environment to your new template and then it will inform you the steps that it's going to take in order to implement your change

4. StackSet:
- A stack set is a collection of stacks and it allows you to create stacks across AWS regions using a single CloudFormation template.
- These resources are defined by the stack in that CloudFormation template. This is the template of the stack, not the stack set

- You can create, update and delete stacks in the target accounts and regions you specified in the template for the stack set 
and this is a regional resource, so if you create a stack set in Ohio, you can manipulate that stack set in Ohio but you cannot 
manipulate it in Northern Virginia. 

- However the stack set changes can deploy resources in other region. We create or rather execute the stack set and its going to deploy these four stacks, we update the stack set, it goes and changes the four stacks in all region.delete stacks set, all of those stack can be deleted.

### CloudFormation Designer:
It's a graphical user interface within the AWS web console that allows you to create a stack. Simply drag and drop AWS resource 
from the pivot to create the stack. There is also text editor so you can manipulate both via UI and editor.

### Getting Started

### Best Practices
- Use I AM control access for cloud formation(create,update,delete stack)
- Reuse template to replicate stacks in multiple environment. (e.g) Use template created for PROD to create environment for QA, development.
- Use Stack sets for cross region. (e.g) Ohio, and these resources in Frankfurt. 
- Use nested stacks to reuse common template patterns.
- Isolate templates to single function. (e.g) Create a VPC template and reuse within your overall template.
- Use CF template with Service Catalog.<br> 
[Note]: Service Catalog it allows administrators to create catalogs of services that users have visibility to. So you can say, User John has access to VPC and EC2. And, there's a custom portal that he can access where he only sees those two services
- Do not embed credentials in your templates.
- Use AWS specific paramter types.
- Use parameter constraints.
- Use AWS::CloudFormation::init to deploy software applications on Amazon EC2 instances.
- Use the latest helper(cfn-init, cfn-signal, cfn-hup) scripts
- Validate template before deploying it to PROD.
- Manage all stack resources through AWS CloudFormation.
- Create change sets before updating your stacks
- Use Stack policies to restricte a particular resource within the stack.<br>
 [Note]:  if you have an EC2 instance that for some reason has very critical data on it, then it's possible to, when updating a stack, to have that instance restarted and you lose that data, a stack policy can ensure that that is restricted and that an update to the stack is not going to impact that particular host

- Use AWS CloudTrail to log AWS CloudFormation calls.
- Use revision controls to manage templates.
- Update your Amazon EC2 Linux instances regularly.(e.g) run yum update/ app update, app upgrade depending up on the OS. 



## Resources
- [AWS CloudFormation UserGuide Getting Started]( https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/gettingstarted.templatebasics.html)
- [AWS Template Resources](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)