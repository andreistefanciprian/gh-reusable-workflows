
# Description

Reusable GitHub Actions workflows

## .github/workflows/flux_k8s_manifests_oci_push_to_gar.yaml

This GitHub Actions reusable workflow automates pushing OCI (Open Container Initiative) images to Google Artifact Registry.
The OCI image is generated using `flux push artifact` command.

##### Inputs

| Name       | Description                               | Required | Type   |
|------------|-------------------------------------------|----------|--------|
| app_name   | Name of the application/service           | Yes      | string |
| build_id   | Unique build identifier                   | Yes      | string |

##### Secrets Required

| Name                        | Description                                           |
|-----------------------------|-------------------------------------------------------|
| ARTIFACT_REGISTRY_HOST_NAME | Hostname of Google Artifact Registry                  |
| PROJECT_ID                  | Google Cloud Platform project ID                      |
| WI_POOL_PROVIDER_ID         | Workload Identity Pool Provider ID for authentication |
| PACKAGER_GSA_ID             | Service account ID for Google Cloud services          |

##### Example Usage

- [Caller Workflow](https://github.com/andreistefanciprian/demo_slack_bot/blob/main/.github/workflows/call_flux_k8s_manifests_oci_push_to_gar.yaml)


## .github/workflows/build_and_push_docker_image_to_gar.yaml

This GitHub Actions reusable workflow automates pushing Docker images to Google Artifact Registry.
The Docker image is built using a Dockerfile and pushed to the registry using `docker push` command.

##### Inputs

| Name      | Description                            | Required | Type   |
|-----------|----------------------------------------|----------|--------|
| app_name  | Name of the application/service        | Yes      | string |
| build_id  | Unique build identifier                | Yes      | string |

##### Secrets Required

| Name                        | Description                                           |
|-----------------------------|-------------------------------------------------------|
| ARTIFACT_REGISTRY_HOST_NAME | Hostname of Google Artifact Registry                  |
| PROJECT_ID                  | Google Cloud Platform project ID                      |
| WI_POOL_PROVIDER_ID         | Workload Identity Pool Provider ID for authentication |
| PACKAGER_GSA_ID             | Service account ID for Google Cloud services          |
| IMAGE_REPO_ID               | Repository ID for storing the Docker image            |

##### Example Usage

- [Caller Workflow](https://github.com/andreistefanciprian/demo_slack_bot/blob/main/.github/workflows/call_build_and_push_docker_image_to_gar.yaml)
