# Assignment 3: Expose NGINX with ClusterIP Service
---

### What I Did

3### 1. Created a Deployment YAML

I wrote a file `nginx-deployment.yaml` that sets up a Deployment with two replicas of the NGINX container. Each pod exposes port 80.

#### 2. Created a Service YAML

Then I created `nginx-service.yaml` to define a ClusterIP Service. This service uses a label selector to discover the pods created by the Deployment and exposes them on port 80 inside the cluster.

#### 3. Applied the Files

I used `kubectl apply` to deploy both YAMLs:

```bash
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml
```

#### 4. Verified the Setup

To confirm everything was working:

- I ran `kubectl get all` to check if the Deployment, Pods, and Service were created.
- I used `kubectl describe service my-nginx-service` to check if endpoints were discovered.
- I used `kubectl get pods -o wide` to check pod IPs, and confirmed they matched the service endpoints.

#### 5. Exported the Live Deployment

I fetched the live YAML of the running Deployment:

```bash
kubectl get deployment my-nginx-deployment -o yaml > nginx-deployment-live.yaml
```

This allowed me to compare the live state with my original spec.

#### 6. Cleanup

After verification, I deleted the resources:

```bash
kubectl delete -f nginx-service.yaml
kubectl delete -f nginx-deployment.yaml
```

---

### Key Learnings

- How Deployments maintain the desired state in Kubernetes.
- How Services use label selectors to expose Pods.
- How to use `kubectl` commands to verify connectivity.
- The difference between written YAML specs and the live cluster objects.

---

This task helped me understand how Kubernetes objects interact to deliver internal service discovery and routing of traffic between pods using services.
