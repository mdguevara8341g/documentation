---
description: 'Deploy Now allows you to deploy from one repository to multiple web spaces. This eases central management of multiple, customized instances.'
sidebar: 'docs'
prev: '/docs/staging-deployments/'
next: '/docs/domain-tls/'
editable: true
---

# Multi deployments
  
Staging deployments give you the ability to build and deploy branches in addition to your main branch. This allows you to stage changes before merging them to production, giving colleagues or customers the option to test and provide feedback. By default, new branches get deployed automatically and receive preview URLs. As Staging Deployment are not meant to be visible for website visitors, you cannot connect them with custom domains. If you are happy with your changes, simply roll them out by merging the branch to production.

:::tip
Multi Deployments are only available for projects running under the [v2 workflow](/docs/git-integration/#v2-projects-created-from-112022). Projects created under v1 need to be switched to v2 manually or by re-creating them. 
:::

~~~mermaid
graph TD
    A(local workspace):::active -->|push to branch A| B(GitHub repository):::active
    B -->|on push| C{Deploy Now}:::active
    C -->|deploy main| D([production]):::inactive
    C -->|deploy branch A| E([stage 1]):::active
    C -->|deploy branch N| F([stage x]):::inactive
    D --> D1([custom domain])
    E --> E1([preview URL]):::active
    F --> F1([preview URL])
~~~

