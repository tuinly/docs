---
sidebar_label: Next.js Static Website
---

# Next.js Static Website

A **Next.js static website** is a type of web application built using the Next.js framework that serves pre-rendered HTML pages. These pages are generated at build time, meaning the content is prepared in advance and stored as static files (HTML, CSS, JavaScript). This approach provides several benefits:

1. **Performance**: Since the pages are pre-generated, they can be delivered to users very quickly without waiting for server-side rendering or database calls. Content is served directly from a Content Delivery Network (CDN), ensuring fast load times.
   
2. **Scalability**: Static websites are highly scalable because the same pre-built files can be served to an unlimited number of users, reducing server load.

3. **SEO-Friendly**: Since Next.js pre-renders pages, the content is available immediately when search engines crawl your site, improving search engine optimization (SEO).

4. **Security**: Without server-side logic, there are fewer attack vectors, making static sites inherently more secure.

In a typical Next.js static site, features like dynamic routing, image optimization, and static export are used to create modern, highly optimized, and responsive websites without relying on a backend server during runtime.

## Reference

### Parameters

- **Deployment Name**: The deployment name uniquely identifies a stack within your Tuinly tenant. It should be descriptive yet easy to understand, allowing you to quickly recognize the purpose or function of the deployment at a glance. A sanitized version will be used as your new repository's name.

- **GitHub Integration**: Selection of your **Tuinly GitHub Integration**.

- **Infra Deployment**: Selection of your AWS infra, the application will be deployed to.

- (Optional) **Custom Domain**: A custom domain can be specified. Currently, only a single custom domain is supported.

- (Optional) **ACM Certificate ARN**: ARN of AWS Certificate Manager certificate. Certificate must include the specified custom domain. Required if custom domain is provided.

## Change Log

### 0.1.0 - Initial release
