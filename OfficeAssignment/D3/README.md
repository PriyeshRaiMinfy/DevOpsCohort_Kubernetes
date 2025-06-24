# Assignment D3: Exposing NGINX Deployment with Service – Summary

### Objective

Expose the NGINX Deployment using a Kubernetes Service of type NodePort to allow access from outside the cluster.

---

### I faced a few issues:

- Initially tried to access the pod directly using its IP, which failed since it's only reachable inside the cluster.
- Learned the difference between ClusterIP, NodePort, and how `minikube service` simplifies testing.

---

## Steps Followed

```bash
kubectl apply -f service.yaml
kubectl get svc
minikube service nginx-service
```

---

### 📸 Screenshots

> ![Service Created](./images/d3-service-created.png)  
> ![Service Access](./images/d3-service-access.png)  

---

### 📤 Output Samples

```
service/nginx-service created

NAME            TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
nginx-service   NodePort   10.96.0.1      <none>        80:30080/TCP   10s
```

---

### Note

```
This assignment helped me understand how networking works in Kubernetes. I also practiced accessing services using both port-forwarding and NodePort.
```