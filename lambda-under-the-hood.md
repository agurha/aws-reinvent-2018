# Lambda Under the Hood

- Control Plane
    -- dev tools - lambda console, sam CLI
    -- control planes APIs - config, resource mgt
- Data Plane
    -- Async invoke and Events - pollers, state managers, leasing service
    -- synchronous invoke - front end, counting, worker

## Workers and such

- when an invoke comes in, a work is establisehd with a sandbox for some time-bound lease
- worker itself has your lambda code, lambda runtime, guest OS, hypervisor, host OS, and hardware
- guest OS is amazon linux
- sandbox does isolation using linux containers
- **NOW using Firecracker: https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/**
- Utilization
    -- concentrates load instead of load balance... cache locality, ability to autoscale
    -- pack server with many different types of loads.. since theyll be doing different things and avoid bottlenecks that many similiar workloads would cause
    -- placement opitmization: pikc workloads taht work together well
- VPC + lambda
    -- currently create ENI and local NAT to connect lambda to VPC
    -- in 2019, will change from ENI to remote NAT shared across workers
- Firecracker = lower startup time, lower memory overhead, more flexibility
- 