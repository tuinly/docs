---
sidebar_label: AWS GitHub OpenID Connect Provider Link (Extension)
---

# AWS GitHub OpenID Connect Provider Link (Extension)

OpenID Connect (OIDC) enables your GitHub Actions workflows to securely access AWS resources without the need to store long-lived AWS credentials as GitHub secrets. This approach ensures temporary, secure access while eliminating the risk of credential exposure.

To learn more about security hardening with OIDC visit the [official GitHub documentation](https://docs.github.com/en/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect) and [official AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc.html).

> **Important**: AWS only allows a single OpenID Connect (OIDC) provider of a specific type (in this case, GitHub) per account. The AWS GitHub OpenID Connect Provider Link (Extension) is designed for cases where a GitHub OIDC provider has already been manually set up — this is common when sharing an AWS account across multiple Tuinly tenants or using the AWS account with other Tuinly AWS infrastructure stacks. If you're setting up the provider for the first time, please use our [AWS GitHub OpenID Connect Provider (Extension)](./aws-github-oidc-provider-ext) instead..

## Reference

### Parameters

- **Infra Deployment**: Selection of your AWS infra, the GitHub OpenID Connect Provider will be linked to.

- **OICD Provider ARN**: Amazon Resource Name (ARN) of the GitHub OpenID Connect Provider you want to link.

## Change Log

### 0.1.0 - Initial release
