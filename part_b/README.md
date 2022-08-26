# creating (based on a local machine, using Minikube)
docker build -t ldapapp .
minikube image load ldapapp
kubectl create secret generic openldap --from-literal=adminpassword=adminpassword --from-literal=users=user01,user02 --from-literal=passwords=password01,password02
kubectl apply -f .
# please wait for a few seconds for the pods to start
kubectl port-forward <ldpa-pod-name> 5000:<any-port-wished>

# cleaning
kubectl delete deployments.apps --all
kubectl delete secrets --all
kubectl delete service --all

# if port forwarding still remains
# kill port forward
ps -ef|grep port-forward
kill -9 <process number>