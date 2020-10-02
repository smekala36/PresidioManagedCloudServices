# CloudFormation Demo

As a way of demonstrating your skill level with AWS and Infrastructure-as-Code in general (CloudFormation, Bash, and Git, in particular), please take the following actions:

  1. Fork this repository and start a new branch in your copy.
  2. In your new branch, add:
     - A CloudFormation template (written in YAML)
     - A bash script that will deploy your template (assume the environment is configured with credentials already)
  3. Commit to your branch (you could use multiple commits as you progress) and push to your copy of this repository on GitHub.
  4. Open a pull request from your repository to this one.
  
## What should go in your CloudFormation template?

Your template should provision the following resources:

  1. A KMS Key
  2. A Secrets Manager Secret
     - With a dynamically generated secret (encrypted by the Key in #1)
  3. An EC2 Instance
     - Use whatever AMI seems reasonable to you
     - Assume a VPC already exists and set the instance's subnet using a parameter     
     - Supply a User Data script that reads the Secret value from #2 when the instance starts up and echos the Secret value to a file
  4. An IAM Role and IAM Instance Profile
     - The Instance Profile should be by the EC2 Instance
     - Permissions granted to the Role should allow it access to read the Secret
  5. A Security Group
     - This should be used by the EC2 Instance
     - It should allow limited inbound traffic
     - It should allow all outbound traffic
     - Assume a VPC already exists and the security group's vpc using a parameter

Add any other parameters or outputs that seem right to you.  If this is too easy, enhance and make it your own. :)

## Ask Questions

Feel free to ask questions to clarify anything that is unclear about these instructions.
