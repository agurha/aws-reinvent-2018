# Networking Foundations - Chalk Talk

**email: mlehwess@amazon.coms**

lol this one was a bit deep into networking

## Transit Gateway
- Transit Gateway is per account.. not VPC.  .. it connects VPCs
- VPC peering was legacy option... lot of overhead/management
- NOTE: we use account / BSA.. not VPC.. so this won't work, will it?
    -- how are we supposed to talk between accounts?
- uses route table to allow policy controls between VPCs.. and close some things off
- allows for single VPN connection between VPCs
- Direct Connect does not YET talk to Transit Gateway.. but coming soon
- net303 from 2018 .. net305 from 2017... has other slides

## Transit VPC

- fixes peering problem before VPC peering .. uses instances
- DX Gateway (Direct Connect) kind of solves this
- can mix w. transit gateway

## Rout53 / Global Accelerator

- allows common IPs across geo

## VPC Sharing

- share VPCs across account
- refer to NET303
- owner/participant relationship
- can do transit gateway with VPC sharing to act as VPC hub