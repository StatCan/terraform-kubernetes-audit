# Terraform Kubernetes Audit

## Introduction

This module deploys and configures Auditing inside a Kubernetes Cluster.

## Security Controls

The following security controls can be met through configuration of this template:

* TBD

## Dependencies

* None

## Optional (depending on options configured):

* None

## Usage

```terraform
module "kubectl_audit" {
  source = "github.com/canada-ca-terraform-modules/terraform-kubernetes-audit?ref=v1.0.1"

  dependencies = [
    "${module.namespace_monitoring.depended_on}",
  ]

  kubectl_service_account = "tiller"
  kubectl_namespace = "monitoring"
}
```

## Variables Values

| Name                    | Type   | Required | Value                                                  |
| ----------------------- | ------ | -------- | ------------------------------------------------------ |
| dependencies            | list   | yes      | Dependency name refering to namespace module           |
| kubectl_service_account | list   | yes      | The service account for kubectl to use                 |
| kubectl_namespace       | list   | yes      | The namespace kubectl will install the manifests under |

## History

| Date     | Release    | Change                                                     |
| -------- | ---------- | ---------------------------------------------------------- |
| 20200823 | v1.0.0     | 1st release                                                |
| 20200824 | v1.0.1     | 1st release                                                |
