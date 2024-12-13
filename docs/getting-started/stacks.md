---
sidebar_position: 40
sidebar_label: Deploy your first Stacks
---

# Deploy your first Stacks

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

### Infrastructure

For the purposes of this guide, we’ll deploy a simple [AWS Account Link](../stacks/infra/aws-account-link) (instead of a full [AWS Landing Zone](../stacks/infra/aws-landing-zone)) as it offers the greatest compatibility. FYI, an AWS Account Link doesn't deploy any actual resources but serves as the infrastructure foundation for workloads running in a specific AWS account.

Afterwards, we deploy an [AWS GitHub OpenID Provider](../stacks/infra/aws-github-oidc-provider-ext.md). This Tuinly Extension enables your GitHub Actions workflows to securely access AWS resources without the need to store long-lived AWS credentials as GitHub secrets. This approach ensures temporary, secure access while eliminating the risk of credential exposure.

In a later section, we'll show you how to optionally destroy all resources created during this guide. Feel free to explore and experiment with different infrastructure stacks afterward!

Let's go ahead and deploy your [AWS Account Link](../stacks/infra/aws-account-link):

1) Navigate to your Tuinly tenant's infrastructure overview.

1) Click **+ Deploy new** to open the infrastructure catalog.

1) Search for the "AWS Account Link" Stack and click "+ Deploy"

1) Provide a friendly deployment name. We recommend using a clear, unique name such as "AWS DEV Account".

1) Select an AWS primary region. For the getting started guide, this value doesn't matter. In general, we recommend selecting a region that's close to your users. Detailed information about regions can be found in the [official AWS documentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

1) Lastly, select your previously created AWS Integration.

1) Click "Next" to proceed to the review page.

1) Review your inputs and click "Deploy".

You will be redirected to your first infrastructure stack deployment. The status will indicate that it is being deployed in the background. Once the status changes to "Deployed", it is fully set up and ready for use within your Tuinly tenant.

> Tip: Occasionally refresh your page in order to update the deployment's status.

We can now deploy your [AWS GitHub OpenID Provider](../stacks/infra/aws-github-oidc-provider-ext.md):

1) On your AWS Account Link deployment's page, navigate to the "Extensions" tab

1) Click "+ Deploy new" to open the infrastructure catalog again. This time, the catalog will be filtered for extensions.

1) Search for the "AWS GitHub OIDC Provider" Extension and click "+ Deploy"

    > **Important**: You will also find a "AWS GitHub OIDC Provider Link" Extension. It allows you to link an existing (Tuinly or non-Tuinly managed) GitHub OIDC provider. If you haven't set one up yet, you can safely ignore this comment and go ahead with the regular "AWS GitHub OIDC Provider".

1) Select the infra Stack you want to deploy the OIDC provider for. This should be the previously deployed AWS Account Link.

1) Click "Next" to proceed to the review page.

1) Review your inputs and click "Deploy".

You will be redirected to the deployment page for your AWS Account Link. To track the status of the extension, check the Extensions tab. Once the status changes to "Deployed," the OIDC provider will be fully set up and ready for use within your Tuinly tenant.

> Tip: Occasionally refresh your page in order to update the deployment's status.

### Application

Your cloud infrastructure is now fully prepared, allowing you to securely and efficiently deploy and operate workloads. We’re ready for the final step in your Stacks onboarding journey—deploying your first application!

In this guide, we’ll deploy a simple [Next.js Static Website](../stacks/applications/nextjs-static). This website will be hosted on Amazon S3 and delivered via AWS's powerful content delivery network, [Amazon CloudFront](https://aws.amazon.com/cloudfront/). Despite its impressive performance and global reach, this serverless solution is a cost-effective way to host static websites. You’ll see how quickly it can be set up!

Let's get started:

1) Navigate to your Tuinly tenant's applications overview.

1) Click **+ Deploy new** to open the applications catalog.

1) Search for the "Next.js Static Website" Stack and click "+ Deploy"

1) Provide a friendly deployment name. This name will also be sanitized and used as your new repository's name. We recommend using a clear, unique name such as "My Getting Started Website".

1) Select the GitHub integration you configured in the last chapter.

1) For "Infra Prod", select the previously deployed AWS Account Link

    > If the AWS Account doesn't show up, make sure to refresh your page. If it still doesn't show up, make sure your AWS Account Link and OIDC provider extension deployments were successfully deployed.

1) Click "Next" to proceed to the review page.

1) Review your inputs and click "Deploy".

You will be redirected to the application deployment page, where you can monitor the deployment progress.

> Tip: Refresh the page occasionally to ensure the status is up-to-date.

Once the status changes to "Deployed", head over to the "Details" tab. Here, you’ll find important information relevant to your stack, such as links to the newly created GitHub repository and deployed website! However, keep in mind that while the website's URL is generated immediately, it may take a bit of time before it’s live. This is because a GitHub Actions workflow is currently running in the background and deploying the latest code to your site. Follow the GitHub repository link from the "Details" tab to track the deployment progress in GitHub Actions.

> **Important**: Although it looks easy and super straightforward, deploying a CloudFront distribution involves updating a global content delivery network. Bring some patience, grab a coffee, it might take a few minutes...
