# Tutorial: Build your online resume using Azure Static Web Apps

In this tutorial, we will build an online resume from [template](https://github.com/wenwei-lin/resume-template/generate) and deploy it to Azure using Azure Static Web Apps service.

Before following this tutorial, make sure you have fulfill the prerequisites:

- A modern web browser like [Microsoft Edge](https://www.microsoft.com/edge?WT.mc_id=academic-51109-ornella) or [Google Chrome](https://www.google.com/chrome/)
- [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=academic-56895-chnoring)
- [Azure Static Web Apps VS Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestaticwebapps&WT.mc_id=academic-56895-chnoring)
- [Git](https://git-scm.com/downloads)
- Azure account ([Free account](https://azure.microsoft.com/en-us/free/) or [Student account](https://azure.microsoft.com/en-us/free/students/))
- [GitHub account](https://github.com/)

Now, let start the journey!

## Step 1: Create an resume from template

Designing an resume website is a time-consuming work. To give you a kickstart, I create a resume template for you. 

Navigate [Create a New Repository from wenwei-lin/resume-template](https://github.com/wenwei-lin/resume-template/generate) page, and fill in *Repository name* to create the resume repo in your GitHub. You can set the repository availability as either Public or Private.

![Create resume repo](img/create-template.png)

Click ***Create repository from template*** button to continue.

## Step 2: Clone the repo to your PC

Next, we will clone the resume repository to our local PC.

> Note  
> You should make sure you have configured GitHub SSH connection.  
> Check out [GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh) for more details.

**Click *Code* in your repo and copy the ssh link.**

![](img/copy_repo_url.png)

**Open Shell in your computer and clone the repo to the location you like.**

```bash
$ git clone <repo_url>
```

![](img/clone.png)

## Step 3: Create an Azure Static Web Apps Service for your resume

Azure Static Web Apps service will host your website on Azure. After that, you can visit your website online. Let's make it!

Change your current directory to the repo, and use `.code` command to open Visual Studio Code.

```bash
$ cd <repo_name>
$ code .
```

![](img/vscode.png)


1. **Install Azure Static Web Apps extension in Visual Studio Code**

![](img/install_extension.png)

2. Once completing, select the Azure logo in the Activity Bar to open the Azure extensions window.

![](img/azure.png)

> **Note: You are required to sign in to Azure and GitHub in Visual Studio Code to continue. If you are not already authenticated, the extension will prompt you to sign in to both services during the creation process.**

3. Under the Static Web Apps label, select the plus sign.

![](img/select_static.png)

4. Next, name your application.

Type resume and press <Enter>.

![](img/app-name.png)

5. Select a region close to you.

**Note: Azure Static Web Apps globally distributes your static assets. The region you select determines where your optional staging environments and API function app will be located.**

![](img/region.png)

8. Select Custom

![](img/custom.png)

Enter / as the location for the application files and press \<Enter\>.

![](img/location.png)

This app does not produce a build output. Ensure the build output location is empty and press \<Enter\>.

![](img/output.png)

9. Select “Open Actions in GitHub.” This will launch the GitHub Actions tab in your browser. You will see the workflow run as it is creating the app. When your webapp is built and deployed, you will see a check for the workflow run.

![](img/open-github.png)

Once the app is created, navigate back to Visual Studio Code - a confirmation notification is shown there. The Visual Studio Code extension also reports the build status to you as the deployment is in progress – and will update you when your app is built and deployed.

![](img/complete.png)

Once the deployment is complete, you can navigate directly to your website.

10. To view the website in the browser, right-click on the project in the Static Web Apps extension, and select Browse Site.

![](img/browse.png)

Your site will look like this:

![](img/site.png)


## Step 4: Customize your resume with Visual Studio Code and push the change

Every time you push the change to your GitHub repository, it will automatically trigger a GitHub action to deploy your website. Let's walk through it.

1. Customize the resume

Open `index.html` in editor, and replace default value, like 'YOUR NAM', 'YOUR TITLE', etc. with your information.

After customization, open the `index.html` with the browser, and your resume will look like this:

![](img/resume_look.png)

2. Push the change to GitHub

Open a new terminal in Visual Studio Code,

![](img/new-terminal.png)

and enter the following command to commit and push the change.

```bash
$ git commit -a -m "Customize my resume"
$ git push
```
![](img/commit-change.png)

3. Wait for deployment

Navigate to your **GitHub repository - Actions**, wait for the deployment. It will take 1~2 min.

![](img/github-action.png)

Now visit your website again, your resume has updated!

![](img/updated.png)

## Next 

Congrats! You have created your resume site. It's time to share the link with your friend!

If you own a domain, you can bind this web with it. [Check this doc for more information](https://docs.microsoft.com/en-us/azure/static-web-apps/custom-domain).