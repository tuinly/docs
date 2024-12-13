---
sidebar_label: Amazon Web Services (AWS)
---

# Amazon Web Services (AWS)

Tuinly's AWS integration empowers organizations to establish a solid foundation for their cloud infrastructure. It starts by enabling self-service AWS landing zones, which provide a scalable and secure multi-account setup, tailored to your organizational needs. This ensures that you adhere to best practices right from the start of your cloud journey.

From there, Tuinly assists in deploying well-architected workloads, ensuring your applications and systems are optimized for performance, reliability, security, cost-effectiveness, and operational excellence — key pillars of [AWS's Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html).

Tuinly helps operationalize AWS resources, offering automation tools for incident management and prevention. This ensures that potential issues are identified early and resolved efficiently, reducing downtime and keeping your AWS environment running smoothly. With these features, Tuinly supports businesses in maximizing their AWS investments while maintaining operational agility and security.

## Security Primer

In line with our best practices, credential sharing should be avoided whenever possible. Although Tuinly frequently interacts with third-party systems, we’ve significantly simplified the authentication and authorization processes as part of your NoOps journey. This is achieved through:

- [AWS Security Token Service (STS)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html), which grants trusted entities short-lived, least-privilege credentials, ensuring secure and temporary access.
- Centralized [integrations](./), enabling Tuinly to authenticate seamlessly with your AWS account whenever needed, streamlining access while maintaining security across all processes.

By leveraging these mechanisms, we ensure robust security without the operational burden of managing shared credentials.

## Configuration

### Prerequisites

- AWS account: For more detailed instructions on creating an AWS account, please refer to the [official AWS documentation](https://aws.amazon.com/resources/create-account/).
- Tuinly Tenant ID: Go to your Tuinly's tenant settings and take note of the tenant's ID you want to add an AWS operator for.

### Deploying an AWS operator

1) In the AWS Management Console, navigate to the CloudFormation service.

1) Click **Create Stack** and choose **With new resources (standard)**.

1) In the **Specify template** section provide the following Amazon S3 URL and proceed by clicking **Next**.

    ```
    https://s3.amazonaws.com/opsassets.tuinly.com/AdministratorAccess.json
    ```

    > **Important**: In this example, admin access is granted, allowing your Tuinly tenant not only to deploy resources on your behalf but also to manage and operate your AWS workloads. Rest assured, Tuinly will never deploy anything without your explicit consent and initiation.
    >
    > If needed, AWS permissions can be configured with more granular controls based on your specific use cases. If you have any concerns, please [reach out](https://urls.tuinly.com/contact) — we're happy to work through the details with you and adjust permissions accordingly.

1) Enter a stack name (e.g. "TuinlyOperator") and provide your Tuinly tenant's ID as noted earlier.

1) Optional: Specify tags, permissions, and advanced options.

1) Review and Deploy: Review your configuration, acknowledge any required capabilities (e.g., IAM), and click **Create stack**.

1) After the deployment has finished, take note of the **OperatorRoleArn** value in the Outputs tab.
    
    ![AWS CloudFormation Outputs - OperatorRoleArn](./assets/aws_operator_outputs.png)
    *Figure 1: OperatorRoleArn in AWS CloudFormation Stack Outputs*

### Adding a new Tuinly AWS integration

1) Navigate to your Tuinly tenant's integrations overview.

1) Select **Configure** under AWS integrations.

1) Click **+ Add** to create a new integration.

1) Assign a friendly name to your integration. We recommend using a clear, unique name such as "AWS Root Account".

1) Enter the ARN of the operator created earlier in CloudFormation.

1) Finally, click **Create** to complete the integration setup.

Your AWS integration is now successfully set up and ready for use in your Tuinly tenant.
