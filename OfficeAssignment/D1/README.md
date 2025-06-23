✅ Step-by-Step Assignment (as given):
✅ Step 1: Create the Pod YAML
You've already created this:

yaml
Copy
Edit
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx-container
    image: nginx:1.14.2
    ports:
    - containerPort: 80
✅ Saved as: pod.yaml

✅ Step 2: Apply Manifest
In your VS Code terminal:

bash
Copy
Edit
cd Kubernetes_Assignment/OfficeAssignment/D1
kubectl apply -f pod.yaml
Expected Output:

bash
Copy
Edit
pod/nginx-pod created
✅ Step 3: Inspect the Pod
Check status:

bash
Copy
Edit
kubectl get pods
Check wide details:

bash
Copy
Edit
kubectl get pods -o wide
View logs:

bash
Copy
Edit
kubectl logs nginx-pod
Describe pod (for debugging):

bash
Copy
Edit
kubectl describe pod nginx-pod