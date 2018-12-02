# Advanced Infrastucture as Code

https://github.com/awslabs/aws-cdk

 - CDK (CLoud Development Kit) using Typescript and others.. allows imperative stuff on CloudFormation
 - still uses yaml/json to get the existing stuff e.g. dependency graph, rollback, etc.

 ## Declarative Macros
 - macro: "AWS::CloudFormation::Macro" can be deployed and called from CF template
 - arbitrary code can be run (in a Lambda)
    -- this could be a security concern
 - some base macros e.g. `StringMacro` for lower, upper, etc.

 ### `Globals` macro
 ```
 Globals:
    SomeText: some-text
    ThingTag: Thing
        Key: Thing
        Value: This is a thing
Resources:
    Bucket:
    ....
        BucketName: "@SomeText"
        Tags:
            - "@ThingTag"
```

## Imperative

- CDK currently in dev preview
- "CloudForm" is TS project separately form CDK
- CDK install: `npm install -g aws-cdk`


## Use Cases

- enforcing attributes before creation e.g. encryption of S3 buckets
- duplicating resource
- dynamically generating tags as comma-delimited strings