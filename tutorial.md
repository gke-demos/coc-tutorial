# See Container-Optimized Compute In Action

## Overview

This tutorial demonstrates the near real-time scaling capabilities of Container-Optimized Compute, which is the default compute for GKE Autopilot mode.

### Ready?

Let's get started!

## Prerequisites

- Enable the Google Kubernetes Engine API
- Create a GKE cluster in Autopilot mode
- Get credentials to access your cluster

### Enable the GKE API

```bash
gcloud services enable container.googleapis.com
```

### Create a GKE cluster

```bash
gcloud container clusters create-auto democluster --location us-central1 --release-channel rapid
```

#### Note
This tutorial uses `us-central1` as the location, but you can replace with your location of choice.

### Generate credentials

```bash
gcloud container clusters get-credentials democluster --location us-central1
```

## Deploy the sample application

```bash
kubectl apply -f manifests/ping-demo.yaml
```

### Wait for the sample application to start

```bash
watch kubectl get pods
```

