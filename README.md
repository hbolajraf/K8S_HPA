## Kubernetes Configuration Files for Horizontal Pod Autoscaler (HPA)

## Overview

This repository contains Kubernetes manifests to demonstrate the configuration of the Horizontal Pod Autoscaler (HPA). HPA automatically scales the number of pod replicas in a deployment based on observed CPU utilization or other select metrics.

## Files

- `deployment.yaml`: Defines the Deployment resource for the application.
- `service.yaml`: Specifies the Service resource to expose the application.
- `ingress.yaml`: Configures Ingress resource for external access to the application.
- `k8s_hpa.yaml`: Contains the HPA configuration to enable automatic scaling.

## Prerequisites

- A running Kubernetes cluster.
- `kubectl` configured to interact with your cluster.
- Metrics Server installed in the cluster to provide resource utilization metrics.

## Usage

1. **Deploy the Application**:

   Apply the Deployment and Service manifests to deploy the application:

   ```bash
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

2. **Configure Ingress (Optional)**:

   If you have an Ingress controller set up and wish to expose the application externally, apply the Ingress manifest:

   ```bash
   kubectl apply -f ingress.yaml
   ```

3. **Set Up Horizontal Pod Autoscaler**:

   Apply the HPA configuration to enable automatic scaling:

   ```bash
   kubectl apply -f k8s_hpa.yaml
   ```

4. **Verify HPA Status**:

   Check the status of the HPA to ensure it's monitoring the application's metrics:

   ```bash
   kubectl get hpa
   ```

   For detailed information:

   ```bash
   kubectl describe hpa
   ```

## Customization

- **Deployment**: Modify `deployment.yaml` to change the application's image, resource requests, and limits.
- **HPA Configuration**: Adjust `k8s_hpa.yaml` to set different metrics, utilization thresholds, or replica counts as needed.


 
