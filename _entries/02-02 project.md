---
sectionid: createproject
sectionclass: h2
title: Create Project
parent-id: lab-ratingapp
---

### Retrieve the login command and token

{% collapsible %}

Once you're logged into the Web Console, click on the username on the top right, then click **Copy Login Command**.

![Copy login command link](media/login-command.png)

> **Note** Some browsers may take you back to the initial OpenShift login screen where you will need select the RHPDS-AAD icon once more.

Click **Display Token**, then copy the command in the section **Log in with this token**.

![Display token](media/token.png)

![Copy login command screen](media/login-command2.png)

Take this login command and paste it into the SSH session we started on the jump host earlier in the prerequisites section.

![OC Login through jump host](media/oc-login.png)

We are now connected to our OpenShift cluster through the jump host.

{% endcollapsible %}

### Create a project

{% collapsible %}

A project allows a community of users to organize and manage their content in isolation from other communities. To create a new project we run the `oc new-project` command followed by the name of the project we would like to create. 

```sh
oc new-project workshop<student#>
```

For example, if you are student 15, the command would be `oc new-project workshop15`

![Create new project](media/oc-newproject.png)


{% endcollapsible %}

> **Resources**
> * [ARO Documentation - Access your services](https://docs.openshift.com/aro/getting_started/access_your_services.html)
> * [ARO Documentation - Getting started with the CLI](https://docs.openshift.com/aro/cli_reference/get_started_cli.html)
> * [ARO Documentation - Projects](https://docs.openshift.com/aro/dev_guide/projects.html)
