# kubernetes cheatsheet

kubectl create -f pod-definition.yml

kubectl get pods

kubectl describe pods mypod1

kubectl delete pods mypod1

#Below commands are for replicacontroller from yaml file

kubectl create -f rc-definition.yml

kubectl get replicationcontroller

kubectl describe rc myapp-rc

kubectl delete rc myapp-rc

#Below commands are for replicaset from yaml file
kubectl create -f rs-definition.yml

kubectl get replicaset

kubectl get pods

kubectl delete replicatset myapp-rs

kubectl scale --replicas=6 -f rs-definition.yml

kubectl replace -f rs-definition.yml

kubectl scale --replicas=6 replicaset myapp-rs

kubectl get rs

kubectl describe rs myapp-rs

kubectl delete rs myapp-rs

#Below commands are for deployments from yaml file
kubectl create -f deployment-definition.yml

kubectl get deployment

kubectl get replicaset

kubectl get pods


#Below commands list all items created
kubectl get all

#namespace creation
kubectl create -f namespace-dev.yml

kubectl create namespace dev



