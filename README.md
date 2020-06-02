# kubernetes cheatsheet

kubectl create -f pod-definition.yml

#pods gets created in default namespace, use --namespace=<> instead

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

kubectl get deployments

kubectl get replicaset

kubectl get pods

#Below commands list all items created

kubectl get all

#namespace creation

kubectl create -f namespace-dev.yml

kubectl create namespace dev

#below will default namespace to actual value to avoid repetition

kubectl config set-context $(kubectl config current-context) --namespace=dev

#list pods across all namespaces

kubectl get pods --all-namespaces

#docker commands

#below commands overrides CMD command and sleeps for defaulted setting.
#ENTRYPOINT ["sleep"]  & CMD ["5"]

docker run --name ubuntu-sleeper ubuntu-sleeper

#below commands overrides entrypoint command and sleeps fpor 10 seconds

docker run  --name ubuntu-sleeper --entrypoint sleeper2.0  ubuntu-sleeper 10

#In kubernetes, command is setting for ENTRYPOINT & args is setting for CMD

#configmaps in declarative way

kubectl create -f configmap.yml

kubectl get configmaps

kubectl describe configmaps

#configmaps in imperative way

kubectl create configmap app-config --from-literal=APP_COLOR=blue \
                                    --from0literal=APP_MODE=dev


kubectl create configmap app-config --from-file=<path-to-file>
