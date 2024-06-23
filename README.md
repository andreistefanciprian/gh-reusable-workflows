
# Description

Reusable GitHub Actions workflows

## .github/workflows/k8s_oci_gar.yaml

This GitHub Actions reusable workflow automates pushing OCI (Open Container Initiative) images to Google Artifact Registry.
The OCIimage is generated using `flux push artifact` command.

### Inputs

| Name       | Description                               | Required | Type   |
|------------|-------------------------------------------|----------|--------|
| app_name   | Name of the application/service           | Yes      | string |
| build_id   | Unique build identifier                   | Yes      | string |

### Secrets Required

| Name                        | Description                                           |
|-----------------------------|-------------------------------------------------------|
| ARTIFACT_REGISTRY_HOST_NAME | Hostname of Google Artifact Registry                  |
| PROJECT_ID                  | Google Cloud Platform project ID                      |
| WI_POOL_PROVIDER_ID         | Workload Identity Pool Provider ID for authentication |
| PACKAGER_GSA_ID             | Service account ID for Google Cloud services          |

### Example Usage

- [Caller Workflow](https://github.com/andreistefanciprian/demo_slack_bot/blob/main/.github/workflows/call_push_oci_gar.yaml)
