# ACM Cluster Placement

This repository provides a sample of placement rules in Advanced Cluster Management (ACM) via OpenShift GitOps.

### Setup

This configuration requires at least 2 clusters that are managed by ACM. The cluster provisioning and configuration via ACM is not covered here.

The *setup* folder has the yaml files required for adding each cluster to GitOps. It also has a quarkus application that is publicly available from *Quay*

The yaml files are:

[ManagedClusterSetBinding](./setup/managed-clusterset-binding.yaml) - binds a ManagedClusterSet resource to a namespace. We are binding this to the *openshift-gitops* namespace

[Placement](./setup/all-clusters-placement.yaml) - Placement allows to select clusters. Here, we are selecting clusters based on label="kss". This placement will only select clusters that have the label "kss"

[GitOpsCluster](./setup/gitops-cluster.yaml) - Registers the clusters selected with the Placement into OpenShift-GitOps (Argo CD)


