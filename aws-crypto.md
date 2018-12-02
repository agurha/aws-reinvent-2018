# Keeping Secrets: SEcuring your Data with AWS Cryptography

https://github.com/aws-samples/aws-reinvent2018-keeping-secrets

Jeff Levine
Ahmed Gouda

- AWS KMS = key manager
    -- regional service
    -- CMKs (customer master keys)
- CLoudHSM = cloud based hardware security module that enable you to easily generate your own keys
- ASM = AWS SEcretes Manager
    -- can write custom lambda functions to rotate custom credentials
- CloudTrail captures the API calls
- CloudWatch catprues relevant API event invokes lambda which uses SNS to send email notifications
- AWS Systems Manager Session Manager provides access to EC2 without SSH keys
- **Warnnig: HSM is pay per hour**
- private interface endpoint: communicate with AWS without going over internet
- fake PEM used in EC2 instance to reference real private key in HSM
    -- openssl dynamic client knows how/where to retrieve real key
    -- "SSL offloading"
- **question:** what is the point of fake PEM if OpenSSL knows how to retrieve it from the EC2 client
- secrets manager defaults to no rotation
- CLI for secrets manager
- rotation function builds lambda function ... can use existing password for admin functions
    -- and triggers first rotation
- currently no load balance integration with HSM
- only use HSM if necessary... meaning private HSM... KMS serves most needs
    -- KMS is level 2
    -- HMS is level 3
- no secrets manager in China
