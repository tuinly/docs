---
sidebar_position: 40
sidebar_label: Deploy your first Application
---

# Deploy your first Application

## What is a Stack?

> **TL;DR**: Tuinly Stacks are a unified way to manage the lifecycle of your cloud infrastructure, platforms, and applications. With full support for diverse technologies and integrations, they empower you to efficiently build, deploy, monitor, and operate your workloads across various cloud environments.

Stacks are the modular building blocks in Tuinly that allow you to deploy cloud infrastructure, platforms, and applications. When combined, these Stacks enable the creation of full-stack cloud workloads. Each stack—whether focused on infrastructure, platforms, or applications—supports a variety of technologies, giving your organization the flexibility to mix and match components based on your specific use case.

For example, you could deploy an Angular, React, or any other web application on a managed Kubernetes cluster, a single-instance VM, or other infrastructure types. These can be hosted on different cloud providers, such as Amazon Web Services (AWS), Google Cloud, and more — allowing for diverse deployment strategies depending on your needs.

### Multi-Technology Support

Stacks accommodate a wide range of technologies, enabling you to build tailored environments. Whether it's deploying a Kubernetes cluster or spinning up virtual machines, Stacks give you the freedom to design workloads your way.

### Integration with Other Services

Stacks represent the resources created in any of your tenant's [integrations](../guides/integrations), such as GitHub or GitLab repositories, AWS Elastic Kubernetes Service (EKS), Google Kubernetes Engine (GKE), and others. These Stacks serve as your **single point of entry** for monitoring, CI/CD pipelines, and configuration.

### Operational Flexibility

Each stack can be enhanced with operational features. For example, a stack linked to a Git repository often comes with features like **pull request** or **commit rollback** operations. When integrated with supported monitoring solutions, this can unlock powerful automation capabilities such as **automated release validations** and **problem remediations** based on real-time monitoring data.

### Unified Management

Stacks consolidate all aspects of your infrastructure, platforms, and applications into one cohesive management point. This allows for streamlined handling of deployments, CI/CD processes, monitoring, and operational tasks—reducing complexity and ensuring smooth workflows.

## Deploy your first stacks

### Getting Started Recap

At this point, you should have set up two key integrations: one that enables you to deploy resources within your preferred cloud provider (e.g. Amazon Web Services (AWS)), and another that connects to your chosen source code management tool (e.g. GitHub). Now, we’ll leverage these integrations to create the essential cloud infrastructure needed to eventually deploy and operationalize your first application.

### Application

Your cloud infrastructure is now fully prepared, allowing you to securely and efficiently deploy and operate workloads. We’re ready for the final step in your Stacks onboarding journey—deploying your first application!

In this guide, we’ll deploy a simple Static Website. This website will be provided by Tuinly's Instant Web Deploy, backed by AWS's powerful content delivery network, [Amazon CloudFront](https://aws.amazon.com/cloudfront/). Despite its impressive performance and global reach, this serverless solution is a cost-effective way to host static websites. You’ll see how quickly it can be set up!

> Coming soon
