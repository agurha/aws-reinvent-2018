# Deep Dive on Amazon Elastic File System (Amazon EFS)

- In October, they added intra-region VPC peering
- Transit Gateway?
    -- connects VPCs!!!
    -- https://aws.amazon.com/blogs/aws/new-use-an-aws-transit-gateway-to-simplify-your-network-architecture/
- performance modes:
    1. general purpose - default, preferred
    2. Max I/O - recommended for scaled out workloads
- throughput modes:
    1. bursting - default
    2. provisioned - higher throughput to storage ratios
- **new -- EFS IA (Infrequent Access)**
    -- cost savings up to 85%
- HIPPA, GDPR, PCI-DSS, SOC, ISO .. compliant
- AWS DataSync
- COST: 
    -- storage: $0.30/GB of storage... for burst
    -- throughput: 
- T-Mobile:
    -- Jenkins cache build dependencies
- Philips:
    -- blah blah blah blah innovation blah blah blah
- best practices:
    - use multiple threads
    - write to multiple directories in parallel
    - use larger IO size (aggregate IO)
    - use Linux kernel 4.3+
    - EFS MOunt helper
    - test with gen purpose perf mode
    - monitor metrics with cloudwatch
- **Cloudwatch automatic dashboards**