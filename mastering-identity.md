# Mastering Identity at Every Layer of the Cake

- cake abstraction 
    -- base = Amazon Web Services - management console, CLI
    -- middle = infrastructure - operating systes, database
    -- application = end user applications
- planes of access
    -- data and control planes
## Builders options (map users to roles)
    -- SAML to IAM
    -- AWS SSO
    -- Custom Broker
- Workshops:
    -- Choose your own SAML adventure
    -- Getting start AWS SSO
- IAM delegatd administartion
    -- admin can grant IAM management permissions but specify a permissions boundary
    -- allow devs to create principals
    -- create boundary and pass role
    -- dev must pass boundary in creation command - `aws iam create-role`
- **Cloud Formation macros less verbose than full IAM role syntax**

## Identity for Infrastructure
- new option = IAM based auth
- `--enable-iam-database-authentication` as an example.. some services require flags to allow this type of auth

## Identity of Infrastructure
- base primitive = IAM roles
- AWS Secrets Manager

### Cognito
- Amazon Cognito = app identity swiss army knife
- vends standard tokens: CUP (i.e. JWT) -- Cognito User Pool, STS tokens
- API Gateway knows about cognito

### service to service
- option: IAM user for service
- option: Client creds using Cognito

# App Identity
- workshop: serverless auth and authorization session/workshop
