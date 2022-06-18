## Edit Deployments
kubectl edit deployment my-deployment

## get info's about all pods
kubectl get pods -o wide

## taint a node
kubectl taint nodes node01 spray=mortein:NoSchedule

## untaint node
kubectl taint nodes controlplane node-role.kubernetes.io/master:NoSchedule-

## label Nodes
kubectl label nodes <node-name> <label-key>=<label-balue>

## How many Labels exist on node
kubectl describe node node01