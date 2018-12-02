# General Notes

- chalk talks were best
- overflow sessions allow easy access to popular sessions
- python serverless microframework= https://github.com/aws/chalice
- talk to someone.. what is our physical implementation?
    - accounts vs VPCs
    - Direct Connect / Transit Gateway
    - how are we supposed to communicate between BSAs?
- **Idea:** series of sessions "Naive Polyglot: <session>"
    - Kubernetes getting started
    - Storage Types for the developer
    - AWS networking for the developers
    - Microservices and Mesh
- AWS Systems Manager Session Manager provides access to EC2 without SSH keys
- **can we use ASM for un/pw?**

# Attended:
- Advanced Infrastructure as Code
- Exploring AWS Global Network
- Deep Dive into S3 Security
- Microservice Mesh
- Mastering Kubernetes on AWS
- ElastiCache Deep Dive
- DynamoDB Deep Dive
- EFS Deep Dive
- Mastering Identity at Every Layer of the Cake
- Networking Foundations - Chalk Talk
- Keeping Secrets: Securing your Data with AWS Cryptos - Chalk Talk

# Great Sessions
1. Exploring AWS Global Network
2. Elasticache Deep Dive
3. DynamoDB Deep Dive (DAT401) *Excellent NoSQL talk*

# Terrible Sessions
1. Deep Dive into S3 Security 
    - not much content
2. Deep Dive into EFS
    - spent more time on customer journey than technical

# Great Articles (rando finds)

- Classic Noun and Verbs article: http://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html
- Resource Modeling: https://www.thoughtworks.com/insights/blog/rest-api-design-resource-modeling
- Classic Intro to SOA: https://dannorth.net/classic-soa/

# AWS Request Signing

- https://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
- "However, when you manually create HTTP requests to access AWS services, you must sign requests that require signing yourself."

```
How Signature Version 4 works

Create a canonical request.

Use the canonical request and additional metadata to create a string for signing.

Derive a signing key from your AWS secret access key. Then use the signing key, and the string from the previous step, to create a signature.

Add the resulting signature to the HTTP request in a header or as a query string parameter.
```

# REST API design

fine graine vs coarse grained
https://www.thoughtworks.com/insights/blog/rest-api-design-resource-modeling
...
"In other words, for complex business processes spanning multiple resources, we can consider the business process as a resource itself. For example, the process of setting up a new customer in a banking domain can be modeled as a resource. CRUD is just a minimal business process applicable to almost any resource. This allows us to model business processes as true resources which can be tracked in their own right."

# OOP

http://www.smashcompany.com/technology/object-oriented-programming-is-an-expensive-disaster-which-must-end

"Industry suffers from the managerial dogma that for the sake of stability and continuity, the company should be independent of the competence of individual employees. Hence industry rejects any methodological proposal that can be viewed as making intellectual demands on its work force. Since in the US the influence of industry is more pervasive than elsewhere, the above dogma hurts American computing science most. The moral of this sad part of the story is that as long as computing science is not allowed to save the computer industry, we had better see to it that the computer industry does not kill computing science."
- Dikjstra

# Storage Types

- file vs object vs block
- https://cloudian.com/blog/object-storage-vs-file-storage/?utm_source=wordpress&utm_campaign=blog-organic&utm_medium=blog&utm_content=object-vs-file
- https://cloudian.com/blog/object-storage-vs-block-storage/