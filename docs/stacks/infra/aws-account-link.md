---
sidebar_label: AWS Account Link
---

# AWS Account Link

An AWS Account Link is like the smaller sibling of an [AWS Landing Zone](./aws-landing-zone). While an AWS Landing Zone provides a comprehensive, pre-configured, and scalable multi-account environment that follows best practices, the Tuinly Account Link offers a simpler but effective way to connect your existing AWS account to Tuinly. Although not as robust as a full Landing Zone, the AWS Account Link serves as a solid foundation for deploying and managing platforms and applications on AWS. Once deployed, it seamlessly integrates your AWS account with Tuinly, enabling streamlined operations and faster deployments.

## Reference

### Parameters

- **Deployment Name**: The deployment name uniquely identifies a stack within your Tuinly tenant. It should be descriptive yet easy to understand, allowing you to quickly recognize the purpose or function of the deployment at a glance.

- **AWS Primary Region**: Specifies the primary AWS region you intend to use. This region will serve as the default location for deploying workloads unless specified otherwise. Note that this selection is not exclusive—other AWS regions remain available and can be utilized for specific use cases, such as disaster recovery or multi-region deployments. Detailed information about regions can be found in the [official AWS documentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

- **AWS Integration**: Selection of a **Tuinly AWS Integration** to link your AWS account with Tuinly. The permissions of the chosen integration will apply to all workloads and operations Tuinly manages within this account. For more details, refer to the [AWS Integration Guide](../../guides/integrations/aws). Ensure the selected integration has the necessary permissions for your intended use case.

## Change Log

### 0.1.0 - Initial release
