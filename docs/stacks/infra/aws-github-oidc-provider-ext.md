---
sidebar_label: AWS GitHub OpenID Connect Provider (Extension)
---

# AWS GitHub OpenID Connect Provider (Extension)

OpenID Connect (OIDC) enables your GitHub Actions workflows to securely access AWS resources without the need to store long-lived AWS credentials as GitHub secrets. This approach ensures temporary, secure access while eliminating the risk of credential exposure.

To learn more about security hardening with OIDC visit the [official GitHub documentation](https://docs.github.com/en/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect) and [official AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc.html).

> **Important**: AWS only allows a single OpenID Connect (OIDC) provider of a specific type (in this case, GitHub) per account. If you’ve previously set up a GitHub OIDC provider manually, for example when you're sharing an AWS account across multiple Tuinly tenants, or are using the account with other Tuinly AWS infrastructure stacks, please use our [AWS GitHub OpenID Connect Provider Link (Extension)](./aws-github-oidc-provider-link-ext) instead. This extension ensures compatibility and seamless integration without conflicting with existing setups.

## Reference

### Parameters

- **Infra Deployment**: Selection of your AWS infra, the GitHub OpenID Connect Provider will be deployed to.

## Change Log

### 0.1.0 - Initial release
