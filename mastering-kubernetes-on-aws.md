# Mastering Kubernetes on AWS

- 51% of kube workloads are on AWS
- networking rules:
    1. no NATing
    2. IP should be common
- EKS uses VPC for networking using CNI Plugin
- Service Types:
    1. CLusterIP
        - internal IP to cluster
    2. Node Port
        - exposes port to outside cluster.. user must handle load balancing
        - uses CLusterIP
    3. LoadBalancer
        - cloud load balancer
        - uses clusterIP and nodeport
    4. NLB - Network Load Balancer
        - currently alpha
        - forwads client IP to node
    5. ExternalName
        - custom DNS name
- AWS Application Load Balancer can do route resolution and forward to relevant services
    -- "ALB Ingress Controller"
    -- now officially supported
- **currently no native solution to provide custom IAM permissions for pods to consume other AWS services**
- some solutions for assume role... kube2iam, kiam, iam4kube, kube-aws-iam-controller
    -- kube2iam really the only one with real production experience
- **OIDC support coming next year**
- control plane vs data plane
- example of implemeting logging wtih:
    1. fluentd 
    2. elasticsearch
    3. kibana - ealstic search visualiation
- **Snap exaple:**
    - chose EKS -- they believe that EKS will stay ahead of vanilla Kubernetes in terms of services (e.g. ALB)
    - data-oriented services
    - using envoy proxy

- read: https://kubernetes.io/docs/concepts/services-networking/service/