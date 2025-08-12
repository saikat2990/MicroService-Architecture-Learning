# Kubernetes Deployment Commands Reference

### Create or Update a Deployment  
Apply a Deployment manifest YAML file to create or update a Deployment in the cluster:

```bash
kubectl apply -f <file.yaml>
```

---

### Update Container Image and Trigger Rollout  
Update the container image for a Deployment, causing Kubernetes to perform a rolling update:

```bash
kubectl set image deployment/<deployment-name> <container-name>=<new-image>
```

---

### Scale Deployment Manually  
Set the number of replicas explicitly for a Deployment:

```bash
kubectl scale deployment/<deployment-name> --replicas=<number>
```

---

### Monitor Rollout Status  
Check the progress and status of a Deployment rollout:

```bash
kubectl rollout status deployment/<deployment-name>
```

---

### Pause an Ongoing Rollout  
Temporarily pause a Deployment rollout to inspect or intervene:

```bash
kubectl rollout pause deployment/<deployment-name>
```

---

### Resume a Paused Rollout  
Continue a paused Deployment rollout:

```bash
kubectl rollout resume deployment/<deployment-name>
```

---

### View Rollout History  
List revisions (update history) of a Deployment:

```bash
kubectl rollout history deployment/<deployment-name>
```

---

### View Details of a Specific Revision  
Show details about a particular Deployment revision:

```bash
kubectl rollout history deployment/<deployment-name> --revision=<revision-number>
```

---

### Rollback to Previous Revision  
Revert the Deployment to the last stable revision:

```bash
kubectl rollout undo deployment/<deployment-name>
```

---

### Rollback to a Specific Revision  
Revert the Deployment to a specified revision number:

```bash
kubectl rollout undo deployment/<deployment-name> --to-revision=<revision-number>
```

---

### Create Horizontal Pod Autoscaler (HPA)  
Autoscale a Deployment based on CPU utilization, setting min and max replicas:

```bash
kubectl autoscale deployment/<deployment-name> --min=<min-replicas> --max=<max-replicas> --cpu-percent=<target-CPU-utilization>
```

---

### List Horizontal Pod Autoscalers  
View all HPAs in the current namespace:

```bash
kubectl get hpa
```

---

### Describe a Horizontal Pod Autoscaler  
Get detailed information about a specific HPA:

```bash
kubectl describe hpa <hpa-name>
```

---

### List All Deployments  
Show all Deployments in the current namespace:

```bash
kubectl get deployments
```

---

### Describe a Deployment  
Get detailed information about a specific Deployment:

```bash
kubectl describe deployment/<deployment-name>
```

---

# Notes

- Kubernetes does **not** automatically rollback failed deployments. You must run rollback commands manually if needed.
- Autoscaling requires metrics-server or a similar component to provide resource usage metrics.
- Rollouts use the RollingUpdate strategy by default, allowing zero downtime by running old and new pods concurrently during updates.

---

If you want this as a Google Docs file, you can upload this markdown to Google Docs or copy-paste the content directly.
