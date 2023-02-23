<h1>IBM Client Engineering - Solution Document</h1>

<h2>IBM CMIS on OpenShift</h2>
<img align="right" src="https://user-images.githubusercontent.com/95059/166857681-99c92cdc-fa62-4141-b903-969bd6ec1a41.png" width="491" >

- [Introduction and Goals](#introduction-and-goals)
  - [Background and Business Problem](#background-and-business-problem)
- [Solution Strategy](#solution-strategy)
  - [Overview](#overview)
  - [Building Block View](#building-block-view)
  - [Deployment](#deployment)
    - [Pre-Requisites](#pre-requisites)
      - [Stage Container Images](#stage-container-images)
        - [Obtain Entitlement Key](#obtain-entitlement-key)
      - [Pull CMIS Image](#pull-cmis-image)
      - [Stage CMIS Image to Artifactory](#stage-cmis-image-to-artifactory)
  - [Security](#security)
  - [Cost](#cost)
  - [Testing](#testing)
- [Architecture Decisions](#architecture-decisions)

# Introduction and Goals

## Background and Business Problem

🚧️

# Solution Strategy

🚧️

## Overview

🚧️

## Building Block View

## Deployment

### Pre-Requisites
#### Stage Container Images
##### Obtain Entitlement Key

1. Go to the [Container software library](https://myibm.ibm.com/products-services/containerlibrary).

2. Click the "Copy key."

3. Copy the entitlement key to a safe place, like a password manager. You will need this entitlement key to login to the IBM Container Registry.

4. (Optional) Verify the validity of the key by logging in to the IBM Entitled Registry using a container tool:

   ```sh
   export IBM_ENTITLEMENT_KEY=the key from the previous steps
   podman login cp.icr.io --username cp --password "${IBM_ENTITLEMENT_KEY:?}"
   ```

> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/light-theme/tip.svg">
>   <img alt="Tip" src="https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/dark-theme/tip.svg">
> </picture><br>
> You can use `podman` or `docker` depending on > how you have set up your environment.

#### Pull CMIS Image
> <picture>
>   <source media="(prefers-color-scheme: light)" srcset="https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/light-theme/info.svg">
>   <img alt="Info" src="https://github.com/Mqxx/GitHub-Markdown/blob/main/blockquotes/badge/dark-theme/info.svg">
> </picture><br>
> At the time of writing, we will work with CMIS Version 3.0.7.0 As part of this solution document. CMIS v3.0.7.0-IF001 will be used to demonstrate rolling upgrades using Jenkins and ArgoCD Pipelines.

- Pull **two** images
  - `ga-307-cmis`
  - `ga-307-cmis-if001`

```
podman pull cp.icr.io/cp/cp4a/fncm/cmis:ga-307-cmis
```

```
podman pull cp.icr.io/cp/cp4a/fncm/cmis:ga-307-cmis-if001
```

#### Stage CMIS Image to Artifactory

🚧️

## Security

🚧️

## Cost

🚧️

## Testing

# Architecture Decisions
