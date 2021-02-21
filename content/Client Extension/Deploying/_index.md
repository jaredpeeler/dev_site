---
title: Deploying
chapter: false
---

Once you've created your custom code and committed it to GitHub, you can now build and deploy.

---
---

## Enabling the Page

The **Deployment** page is not accessible by default. You must enable it in the **Corporate Office Advanced Settings**. 

{{% notice info %}}
Enable the *ViewAdvancedSettings()* permission to access the **Advanced Settings** section. Learn more about [Employee Permissions and Roles](https://help.directscale.com/hc/en-us/articles/360049588994-Assigning-Employee-Permission-Roles).
{{% /notice %}}

To enable:

1. In **Corporate Office**, navigate to: **Administration** > **Advanced Settings** > **Release Toggles**.

    `{Client_ID}.corpadmin.directscale.com/Settings?category=Release%20Toggles`

     ![Release Toggles page](https://lxteam.blob.core.windows.net/images/DevSite/ClientExtension/release%20toggles%20page.png)
2. Locate the **Platform** section.
3. Select **Use Separate Domain**.

    ![Platform section](https://lxteam.blob.core.windows.net/images/DevSite/ClientExtension/platform%20section.png)
4. Click **Save Changes** at the bottom of the page.

{{% notice warning %}}
Only enable the **Deployment** page when you have Extension code ready to commit or errors may occur.
{{% /notice %}}

---
---

## Finding the Page

In **Corporate Office**, navigate to **Administration** >  **Deployment**.

`{client_ID}.corpadmin.directscale.com/Corporate/Admin/Deployment`

In *Unified Admin*, in the **CorpAdmin** module, navigate to: **Developer** > **Deployment**.

`{client_ID}.directscale.com/#/DiscoDeployment`

---
---

## Deploying

{{% notice warning %}}
Attempting to deploy any code with errors can break vital functionality. Always first deploy to your *Stage* environment, if available.
{{% /notice %}}

1. In the **Deployment** page, you may see all your previous builds from GitHub.

    ![Deployment page](https://lxteam.blob.core.windows.net/images/Resources/extensions-module/deployment%20page.png)

    Click **Queue New Build**, to add a new build artifact.

    ![Queue New Build button](https://lxteam.blob.core.windows.net/images/Resources%2Fextensions-module%2Fque-new-buld.png)

    This queues the build across all environments (*Stage*/*Live*).

2. Click **Deploy**.

    ![Deploy button](https://lxteam.blob.core.windows.net/images/Resources%2Fextensions-module%2Fdeploy.png)

    The build only deploys to the current environment. Log into each environment and deploy manually.

    This queues the pipeline, and your new version is ready to use.

The current deployed version displays at the top right of the page:

![Build version](https://lxteam.blob.core.windows.net/images/DevSite/ClientExtension/deployment%20version.png)