# AWS templates

This collection of templates is intended to be used with AWS CloudFormation.

How to use:
* In the region you want to deploy the template to, navigate to the CloudFormation AWS service.
* Create a stack and upload the template of your choice.
* Fill out the parameters.
* Wait for the Deployment to finish.
* Simply delete the stack in CloudFormation if you want to tear down the deployment. Your data will be unaffected.

## Fargate

Requirements:
- A provisioned MySQL instance, accessible from the web. Have the access credentials (host, port, user, password) at hand for setup.
- (optional) An RSA keypair.

What it includes:
- A publicly accessible Prisma container, deployed to AWS ECS Fargate.

What it _not_ includes / caveats:
* The Fargate template only works in supported Fargate regions (N. Virginia / us-east-1 only at the moment).
* You can not deploy more than one container at the moment. Examples for multi-container setup will follow in the future.
* You can not deploy more than one container per database. E.g. If you have a MySQL 
* **It is necessary to use Prisma version 1.6-beta or higher** for Fargate to work.
* The template does not include SSL / Route53 setup.

You can find the endpoint to access your cluster after the template successfully deployed in the template outputs (click on the template, down below: `Outputs`), `ExternalUrl`. Use this URL to link your cluster, or CNAME a custom domain.
