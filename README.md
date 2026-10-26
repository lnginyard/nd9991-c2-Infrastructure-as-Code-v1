# AWS Infrastructure as Code — High-Availability Web Application

A CloudFormation project based on a Udacity Cloud DevOps Engineer course scenario. The goal is to describe and provision the AWS network and compute resources needed to host a web application with a public load balancer and application servers in private subnets.

## What this project is intended to demonstrate

- Infrastructure described as code using AWS CloudFormation
- VPC and subnet design
- Public load balancer with application servers in private subnets
- Security groups and IAM role-based access to S3
- Auto Scaling and health checks
- Parameterized templates and stack outputs
- Repeatable infrastructure creation and teardown

**Portfolio honesty note:** this repository contains course/starter material and its README previously included architecture placeholders. Before describing it as a completed deployment, verify the current template, parameter files, and deployment outputs, then replace this note with the exact resources and tests you personally completed.

## Architecture target

```text
Internet
   |
Public Load Balancer
   |
Private Subnets
   |-- Application Server / Auto Scaling
   |-- Application Server / Auto Scaling
   |
S3 application artifact
```

This is the target scenario described in the project instructions, not a claim that the stack is currently deployed.

## Review checklist

Before using this repository in an application, confirm that the template includes and correctly configures:

- VPC, public/private subnets, route tables, and NAT/egress path as required
- Load balancer listeners and health checks
- Launch configuration/template and Auto Scaling group
- Least-privilege IAM role for application artifact access
- Security group rules that expose only required ports
- Parameters and outputs, including the load balancer endpoint
- Valid CloudFormation syntax and successful stack creation
- A clean teardown path and no leftover billable resources

## How to validate

Use an AWS account/profile you control and understand that deployment can incur charges. Review the template before running any command.

```bash
aws sts get-caller-identity
aws cloudformation validate-template --template-body file://<template-file>.yaml
```

Replace `<template-file>.yaml` with the actual template path in this repository. A successful template validation is not the same as a successful deployment or a security review.

## Learning context

This project is part of a cloud infrastructure learning path. For a recruiter-facing portfolio, pair it with a diagram, concise implementation notes, screenshots or sanitized deployment output, and a list of issues you found and resolved.

## Security

Never commit access keys, passwords, private keys, or account-specific configuration. Prefer named AWS profiles and least-privilege IAM permissions. Remove test infrastructure after validating it.
