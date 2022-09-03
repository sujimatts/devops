# Integrate Microsoft AD with AWS
## Key AWS Services

## AWS Managed Microsoft AD: 
    - lets you run Microsoft Active Directory (AD) as a managed service
    - best choice if you need actual Active Directory features to support AWS applications or Windows workloads, including Amazon Relational Database Service for Microsoft SQL Server. 
    - It's also best if you want a standalone AD in the AWS Cloud that supports Office 365 or you need an LDAP directory to support your Linux
    - easy to set up and run directories in the AWS Cloud, or connect your AWS resources with an existing on-premises 
    - Manage users and groups, Provide single sign-on to applications and services
    
## AD Connector:
    - simply connects your existing on-premises Active Directory to AWS. 
    - AD Connector is your best choice when you want to use your existing on-premises directory with AWS services.
    - proxy service that provides an easy way to connect compatible AWS applications, such as Amazon WorkSpaces, Amazon QuickSight, and Amazon EC2 for Windows Server instances, 
      to your existing on-premises Microsoft Active Directory

## How to choose best service:
    https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html

# How to Setup SSO
 - https://getstarted.awsworkshop.io/02-dev-fast-follow/02-federated-access-to-aws/02-aws-sso-ad.html

  ### AWS SSO [AWS IAM Identity Center is the successor to AWS SSO]
    [ manage SSO access to multiple AWS accounts & business appls]
    
    ![AD_SSO](../ref_images/sso-integration-ad-conenctor.png)

    - AWS Directory Service has the following two options available:

    Create a two-way trust relationship – Two-way trust relationships created between AWS Managed Microsoft AD and an on-premises Active Directory enable on-premises users to sign in with their corporate credentials to various AWS services and business applications. One-way trusts will not work with AWS SSO. For more information about setting up a two-way trust, see When to Create a Trust Relationship in the AWS Directory Service Administration Guide.
    Create an AD Connector – AD Connector is a directory gateway that can redirect directory requests to your on-premises Active Directory without caching any information in the cloud. For more information, see Connect to a Directory in the AWS Directory Service Administration Guide.Note
    
