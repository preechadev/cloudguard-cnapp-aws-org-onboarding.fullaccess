# CloudGuard CNAPP AWS Organization Terraform Onboarding (Full Access Mode)
This Terraform project is intended to be used to onboard an entire AWS organization accounts in one-shot.     
What it does is configuring, via **Terraform**, an existing CloudGuard CSPM Portal and AWS master account.      
 
## How to start?
You would need to have a CloudGuard tenant, you can create one via *Infinity Portal* by clicking: [Register Here](https://portal.checkpoint.com/create-account)

## Get API credentials in your CloudGuard CNAP Portal
Then you will need to get the API credentials that you will be using with Terraform to onboard the accounts.

![Architectural Design](/zimages/create-cnapp-serviceaccount.jpg)

Remember to copy these two values, you will need to enter them in the *.tfvars* file later on.

## Prerequisite
You would need to give as a parameter the External ID that you can obtain in the onboarding wizard:
![AWS External ID](/zimages/aws-external-id.jpg)

You would need to enable Trust Access with AWS Organization:      
![AWS Trust Access](/zimages/aws-enable-trust-access.jpg)

## How to use it
The only thing that you need to do is changing the __*terraform.tfvars*__ file located in this directory.

```hcl
# Set in this file your deployment variables
aws-access-key  = "xxxxxxxxxxxxxx"
aws-secret-key  = "xxxxxxxxxxxxxx"

cspm-key-id     = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
cspm-key-secret = "xxxxxxxxxxxxxxxxxxxx"
cspm-aws-external-id = "xxxxxxxxxxxxxxxxxxxx"

chkp-account-region = "Europe"     // Use either Europe / America / Singapore / Australia or India
```
If you want (or need) to further customize other project details, you can change defaults in the different __*name-variables.tf*__ files. Here you will also able to find the descriptions that explains what each variable is used for.
