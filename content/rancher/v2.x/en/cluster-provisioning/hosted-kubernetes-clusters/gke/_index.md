---
title: Creating a GKE Cluster
shortTitle: Google Kubernetes Engine
weight: 2105
aliases:
  - /rancher/v2.x/en/tasks/clusters/creating-a-cluster/create-cluster-gke/
---

## Prerequisites in Google Kubernetes Engine

>**Note**
>Deploying to GKE will incur charges.

Create a service account using [Google Kubernetes Engine](https://console.cloud.google.com/projectselector/iam-admin/serviceaccounts). GKE uses this account to operate your cluster. Creating this account also generates a private key used for authentication.

The service account requires the following roles:

- **Compute Viewer:** `roles/compute.viewer`
- **Project Viewer:** `roles/viewer`
- **Kubernetes Engine Admin:** `roles/container.admin` 
- **Service Account User:** `roles/iam.serviceAccountUser`

[Google Documentation: Creating and Enabling Service Accounts](https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances)

## Create the GKE Cluster

Use {{< product >}} to set up and configure your Kubernetes cluster.

1. From the **Clusters** page, click **Add Cluster**.

2. Choose **Google Kubernetes Engine**.

3. Enter a **Cluster Name**.

4. {{< step_create-cluster_member-roles >}}

5. Either paste your service account private key in the **Service Account** text box or **Read from a file**. Then click **Next: Configure Nodes**.

	>**Note:** After submitting your private key, you may have to enable the Google Kubernetes Engine API. If prompted, browse to the URL displayed in the Rancher UI to enable the API.

6. Select your **Cluster Options**, customize your **Nodes** and customize the **Security** for the GKE cluster. Review your options to confirm they're correct. Then click **Create**.

{{< result_create-cluster >}}
