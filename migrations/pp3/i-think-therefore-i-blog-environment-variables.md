---
description: >-
  To provide secret keys and some further required configuration details,
  environment variables are added to the service.
---

# Python Essentials: Environment variables

During the development process you may have used a creds.json file which contained sensitive information. For the application to perform correctly, this information is required in the production environment. Luckily, Render provides a couple of ways to give your application access to these details without exposing them to the public.

### Individual Variables

This allows the addition of individual environment variables.

This would be a good place for development and debug variables when needed.

### Secret File

This file will be available 'behind the scenes', it is not accessible to the public so the security and secrecy of its content are maintained.

{% hint style="info" %}
This also acts as a nice backup location of production environment variables should a GitPod workspace be lost without another external backup of the `creds.json` file.
{% endhint %}

### Process

1\. Locate and click "**Advanced**"

<figure><img src="../../.gitbook/assets/advanced.png" alt="Advanced button"><figcaption></figcaption></figure>

2\. Click "**Add Environment Variable**"

<figure><img src="../../.gitbook/assets/env-var.png" alt=""><figcaption></figcaption></figure>

3\. Add the following environment variable

<figure><img src="../../.gitbook/assets/port-8000.png" alt="an environment variable with the left input containing port in uppercase and the right input having a value of 8000"><figcaption></figcaption></figure>

| Key  | Value |
| ---- | ----- |
| PORT | 8000  |

{% hint style="danger" %}
This value is required for the Python mock terminal program - do not change it!
{% endhint %}



{% hint style="info" %}
If your project does not require a `creds.json` file, skip to the next page.
{% endhint %}



4\. Open a new browser tab and navigate to your Heroku dashboard and open the **Settings** tab of your existing app

<figure><img src="../../.gitbook/assets/settings-tab.png" alt="settings tab selected"><figcaption></figcaption></figure>

5\. Click "**Reveal Config Vars**"

<figure><img src="../../.gitbook/assets/reveal-config-vars.png" alt="reveal config vars button"><figcaption></figcaption></figure>

6\. Copy the value of your **CREDS** variable to your clipboard

<figure><img src="../../.gitbook/assets/copy-creds-redacted.png" alt="the value input of the CREDS variable shown highlighted"><figcaption></figcaption></figure>

7\. Back in Render, click "**Add Secret File**"

<figure><img src="../../.gitbook/assets/add-secret.png" alt="add secret file button"><figcaption></figcaption></figure>

8\. Paste in the copied text to the **File contents** text area input and ensure the **Filename** is **creds.json**

<figure><img src="../../.gitbook/assets/secret-file-redacted.png" alt="an example secret file with file name in the upper input and the file contents in lower input"><figcaption></figcaption></figure>

{% hint style="warning" %}
Make sure to click "**Save**" when done.
{% endhint %}

### Up Next

The final option is whether to **Auto-Deploy**. The two options are explained in the following page.
