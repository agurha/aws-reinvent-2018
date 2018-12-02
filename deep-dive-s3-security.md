# Deep Dive into S3 Security

- start with least privilege
- IAM service
- split into two concepts.. principal and bucket itself
    -- who is it and what does the bucket allow
    -- two separate policies
- policies written in JSON
- S3 Access Control lists allow access.. cannot deny.. written in XML
- preferably use bucket policies over ACLs
- pre-signed URLs work as a time-boxed working endpoint
- **block public Access** NEW -- set of 4 security controls
    1. block new public ACLs and uploading public objects
    2. remove public access granted throuhg public ACL
    3. block new public bucket policies
    4. block public and cross-account access to buckets that have public policies
- different management methods for keys around encryption at rest
- default = atuomatically encrypt
- recommend SSE-S3 or SSE-KMS
- audit - CloudTrail, Amazone Macie
- S3 server access logs