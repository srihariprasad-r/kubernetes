# kubernetes cheatsheet

#This command creates replicaset from yaml file
kubectl create -f rs-definition.yml

kubectl get replicaset

kubectl get pods

kubectl delete replicatset myapp-rs

kubectl scale --replicas=6 -f rs-definition.yml

kubectl replace -f rs-definition.yml

kubectl scale --replicas=6 replicateset myapp-rs

