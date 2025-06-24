# Assignment D2: NGINX Deployment on Kubernetes – Summary

### Objective

Create a scalable Deployment for NGINX instead of a single Pod. This introduces ReplicaSets and ensures the application stays available.

---

### I faced a few issues:

- I had to ensure that the selector matched the pod template labels, otherwise, no pods would get created.

---

## Steps Followed

```bash
kubectl apply -f deployment.yaml
kubectl get deployments
kubectl get rs
kubectl get pods
kubectl describe deployment nginx-deployment
```

---

### 📸 Screenshots

> ![Deployment Created](./images/d2-deployment-created.png)  
> ![Deployment Pods](./images/d2-pods.png)  
> ![ReplicaSet](./images/d2-replicaset.png)

---

### 📤 Output Samples

```
deployment.apps/nginx-deployment created

NAME               READY   UP-TO-DATE   AVAILABLE   AGE
nginx-deployment   2/2     2            2           1m
```

---

