---
description: >-
  Hints and tips, and some known common issues to help with deploying on
  Render.com
---

# ‼ Troubleshooting

Sometimes a build will not show any progress, and unfortunately, sometimes it will fail to start at all. You may also receive a 404 error when visiting the deployed link, or find CSS not being applied as expected and other oddities.

### General

#### Wait...a while!

Once the build has started, we suggest continuing with some other activities for around **15 minutes** <mark style="color:red;"></mark> and then attempting to open the deployed site via the **link below your WEB SERVICE name:**

<figure><img src="../.gitbook/assets/deployed-url-arrow.png" alt="deployed URL shown below the web service name"><figcaption></figcaption></figure>

If you leave the console page, you can view the progress of the current deployment via the **Events** tab:

<figure><img src="../.gitbook/assets/events-tab.png" alt="the events tab selected at the top of the menu on the left hand side"><figcaption></figcaption></figure>

The second deployment in the screenshot above is currently in progress, noted by the three dots on the right hand side. To view the console for that build, click **Deploy** on that entry.

Once the build is successful, the deployment will take a few more minutes:

<figure><img src="../.gitbook/assets/build-successful.png" alt="a console showing a build successful message"><figcaption></figcaption></figure>

{% hint style="warning" %}
If the deploy fails for any reason, restart via the Manual Deploy options and select "Deploy latest commit" detailed in [Failed Deployments](troubleshooting.md#undefined) below.
{% endhint %}

#### Deployment Delays

If you believe the deployment has completed and you receive a 404 error, or some styling appears not to have loaded:

Due to the nature of the deployment process, we suggest **waiting a further 10 minutes** and then doing a **cache refresh** of your deployed site. If you are still having issues, please explore the steps below.

### Console

We advise checking the **Events** tab once the <mark style="color:green;">**Build successful 🎉**</mark> message is shown, as the build page does not always update to show **Live**, instead it remains on **…in progress**:

<figure><img src="../.gitbook/assets/in-progress.png" alt=""><figcaption></figcaption></figure>

A successful build in the **Events** tab will show:

<figure><img src="../.gitbook/assets/deploy-live.png" alt=""><figcaption></figcaption></figure>

The build log _may_ update, but not always:

<figure><img src="../.gitbook/assets/build-started.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Clicking **Deploy** on a deployment entry in the **Events** tab will display the build log for that deployment.
{% endhint %}

{% hint style="warning" %}
On occasion, when starting a deployment the console does not update at all. In this instance, we advise restarting the deployment via the Manual Deploy options and select "Deploy latest commit" detailed in [Failed Deployments](troubleshooting.md#undefined) below.
{% endhint %}

### Failed Deployments

If the deployment has failed for any reason, often noted by a red "**Failed**" note on the deployment ![](../.gitbook/assets/failed-deploy.png), follow the steps below:

1. Click "**Manual Deploy**":\
   <img src="../.gitbook/assets/manual-deploy.png" alt="" data-size="original">
2. Click "**Clear build cache & deploy**":\
   ![](../.gitbook/assets/clear-cache.png)
3. Wait for the deployment and watch the console for some activity:\
   ![](../.gitbook/assets/console-activity.png)
4. If the build still fails, you can try selecting "**Deploy latest commit**".

### Branches

If you are familiar with branches:

* If you have Auto-Deploy set to Yes, the automatic deployment will only trigger if you deploy to the relevant branch.
* You have the option of manually triggering a deployment at any time by following the steps in [Failed Deployments](troubleshooting.md#failed-deployments).

### Python Version

By default, Render uses the latest patch version of Python 3.7.

You can customize the Python version for your app by setting the **PYTHON\_VERSION** environment variable to a valid Python version. To do so, open up the **Environment** tab within your Web Service and click **Add Environment Variable**.

<figure><img src="../.gitbook/assets/environment-tab.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/python-version.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
A manual deployment is advised following the modification of any environment variables. Consult the steps in [Failed Deployments](troubleshooting.md#failed-deployments) for guidance on manually deploying.
{% endhint %}
