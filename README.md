# setup-github-webhook-for-Jenkins
Setting up GitHub webhooks for Jenkins allows Jenkins to automatically trigger builds when changes are pushed to your GitHub repository. Here's a step-by-step guide to setting up GitHub webhooks for Jenkins

## Prerequisites
1. Jenkins is installed and running.
2. Jenkins has the GitHub plugin installed.
3. You have administrative access to your GitHub repository.
4. Jenkins is accessible over the network, preferably with a publicly accessible URL.

## Step 1: Configure Jenkins
  - Install GitHub Plugin
  - Go to your Jenkins dashboard.
  - Navigate to Manage Jenkins > Manage Plugins.
  - In the Available tab, search for GitHub Plugin.
  - Install the plugin and restart Jenkins if necessary.

## Create a Jenkins Job:
  - Go to your Jenkins dashboard.
  - Click on New Item and create a new Freestyle or Pipeline job.
  - In the job configuration, under the Source Code Management section, select Git and provide your repository URL.
  - Add GitHub Hook Trigger
In the job configuration, scroll down to the Build Triggers section.
Check the box for GitHub hook trigger for GITScm polling.
Step 2: Configure GitHub Webhook
Go to Your GitHub Repository:

Navigate to your GitHub repository.
Click on Settings > Webhooks.
Add a New Webhook:

Click the Add webhook button.
In the Payload URL field, enter the URL of your Jenkins server followed by /github-webhook/. For example, http://your-jenkins-server/github-webhook/.
Set the Content type to application/json.
You can select Just the push event or choose to send everything for all event types.
Click the Add webhook button to save.
Step 3: Configure Security (Optional but recommended)
Generate a Secret Token:

Generate a secret token that GitHub will use to sign the payloads sent to Jenkins.
In the webhook configuration on GitHub, enter the secret token in the Secret field.
Configure Jenkins to Use the Secret Token:

In Jenkins, navigate to Manage Jenkins > Configure System.
Find the GitHub section and enter the same secret token under GitHub Web Hook.
