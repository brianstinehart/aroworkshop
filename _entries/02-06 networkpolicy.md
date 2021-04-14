---
sectionid: networkpolicy
sectionclass: h2
title: Create Network Policy
parent-id: lab-ratingapp
---

Now that you have the application working, it is time to apply some security hardening. You'll use [network policies](https://docs.openshift.com/aro/admin_guide/managing_networking.html#admin-guide-networking-networkpolicy) to restrict communication to the `rating-api`.

### Switch to the Cluster Console

{% collapsible %}


Navigate to **Networking -> Network Policies** and click **Create Network Policy**.

![Cluster console page](media/cluster-console.png)

{% endcollapsible %}

### Create network policy

{% collapsible %}

You will create a policy that applies to any pod matching the `app=rating-api` label. The policy will allow ingress only from pods matching the `app=rating-web` label.

Use the YAML below in the editor, and make sure you're targeting your project by changing the **namespace** to **workshop<student#>**.

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: api-allow-from-web
  namespace: workshop<student#>
spec:
  podSelector:
    matchLabels:
      app: rating-api
  ingress:
    - from:
        - podSelector:
            matchLabels:
              app: rating-web
```

Click **Create**.

![Create network policy](media/create-networkpolicy.png)

{% endcollapsible %}

> **Resources**
> * [ARO Documentation - Managing Networking with Network Policy](https://docs.openshift.com/aro/admin_guide/managing_networking.html#admin-guide-networking-networkpolicy)
