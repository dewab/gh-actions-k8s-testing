# gh-actions-k8s-testing

## Status

![latest build](https://github.com/dewab/gh-actions-k8s-testing/actions/workflows/k8s_deploy.yml/badge.svg)

## Goals

Workspace to demonstrate the usage of GitHub Actions to deploy a Kubernetes manifest into an on-prem vSphere for Tanzu Cluster.

## Requirements

|Secret|Required|Description|
|---|---|---|
|`KUBE_CONFIG`|Yes|Kube Config file used to deploy manifest.|
|`TANZU_TMC_ENDPOINT`|Yes|Tanzu Mission Control Endpoint (ex. someorganization.tmc.cloud.vmware.com).|
|`TANZU_API_TOKEN`|Yes|Tanzu API Token generated in VMware Cloud Sevices.|

## Kubeconfig

To retrieve the kubeconfig from TMC, you can use the following command:

```bash
tanzu tmc cluster kubeonfig get --management-cluster-name <management-cluster-name> --provisioner <provisioner> <cluster-name>
```

The secret does not require base64 encoding.

## Tanzu Mission Control Endpoint

The Tanzu Mission Control Endpoint can be found in the URL when you access the TMC Console.

## Manually deploy manifest

```bash
kubectl apply -f manifest.yaml
```
