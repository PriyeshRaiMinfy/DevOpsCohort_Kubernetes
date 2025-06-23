Assignment : ngnix deployment

✅ Step 1: Apply the Deployment
bash
Copy
Edit
kubectl apply -f deployment.yaml
-----------------------------ss

2: Verify Deployment, ReplicaSet, and Pods
bash
Copy
Edit
kubectl get deployment
kubectl get replicaset
kubectl get pods
-------------------------------ss


3:   testing autohealing (feature of replica set)
Delete one pod:

bash
Copy
Edit
kubectl delete pod <pod-name>


----------------------------------sss



Scale the Application
Edit the replicas in deployment.yaml:

yaml
Copy
Edit
replicas: 4
Re-apply the file:

bash
Copy
Edit
kubectl apply -f deployment.yaml
Verify:

bash
Copy
Edit
kubectl get pods


--------------------------------------------ss
Clean Up
bash
Copy
Edit
kubectl delete deployment nginx-deployment