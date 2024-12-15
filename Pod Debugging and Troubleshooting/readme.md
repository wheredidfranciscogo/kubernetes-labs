# Kubernetes Pod Debugging and Troubleshooting Lab

## Overview:
In this lab, we learned how to debug and troubleshoot Pods in Kubernetes. We explored various scenarios such as handling invalid images, inspecting Pod logs, and using `k9s` for efficient resource management.

---

## Key Concepts and Tasks:

### 1. Invalid Image in a Pod:
- If you specify an invalid image, Kubernetes will attempt to pull the image and fail. It will show an error like `ErrImagePull` or `ImagePullBackOff`.
- The Pod will remain in a `Pending` state while Kubernetes retries pulling the image.

### 2. CrashLoopBackOff State:
- This state occurs when a container in a Pod crashes repeatedly. Kubernetes restarts the Pod but it keeps failing due to issues like invalid configuration or missing dependencies.

### 3. Inspecting Detailed Events and Errors:
- To troubleshoot Pods, use `kubectl describe <pod-name>` to view detailed events and identify issues such as image pull errors.

### 4. Viewing Logs for a Specific Container:
- Logs can be accessed with `kubectl logs <pod-name>`. If an image is invalid, the logs will show `ImagePullBackOff` errors or may be empty if the container hasn't started.

### 5. Editing a Deployment:
- Use `kubectl edit deployment <deployment-name>` or modify the deployment manifest and apply changes to resolve issues with invalid container images.

### 6. Using k9s:
- **k9s** is a terminal-based UI for Kubernetes. It provides better visibility and easier navigation compared to `kubectl`.
  - To view logs: select a Pod and press `l`.
  - To describe resources: press `d`.
  - Advantages of k9s include quicker navigation between resources and more intuitive management of Pods, deployments, and other resources.

### 7. Basic Kubernetes Concepts:
- **Pod**: The smallest deployable unit in Kubernetes, can contain one or more containers.
- **Deployment**: A higher-level abstraction that manages the state of Pods, such as replicas and updates.
- **ReplicaSet**: Ensures that the specified number of Pod replicas are running at any given time.

### 8. Kubernetes Events:
- Events provide logs of significant occurrences in the cluster, such as image pull failures or container crashes. They help diagnose and troubleshoot issues.

---

## Tools:
- **kubectl**: Command-line tool for interacting with Kubernetes clusters.
- **k9s**: Terminal UI tool for interacting with Kubernetes resources.