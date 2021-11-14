# Voting-Application-K8s
 
 ###  Voting application:
 
 I have used minikube with base operating system Ubuntu to create the voting application using kubernetes. Here i am mainly using the deployment definition files for rplicatset and pods, service definition file for clisterip,nodeport services.
 
 Voting application which consisting f an voting app pod and redis pod for the db, a worker pod to esatablish  the connection from redis to postgres db(used to save the votes count), postgres  db forward the voting result to the result pod.
 
### Installation of minikube:

```
  curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 

 ubuntu@/:~$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 61.0M  100 61.0M    0     0  56.9M      0  0:00:01  0:00:01 --:--:-- 56.9M

ubuntu@/:~$ sudo chmod +x minikube
ubuntu@/:~$ sudo mv minikube /usr/local/bin/
ubuntu@/:~$ minikube version
minikube version: v1.21.0
commit: 76d74191d82c47883dc7e1319ef7cebd3e00ee11
ubuntu@/:~$
```

### Start minikube:

```
sudo su -

root@/:~#  apt install conntrack

root@/:~# minikube start --driver=none
    
root@/:~#  minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured
```

You needs to create the deployent files to create the pods and replicset for each application using in votiong application and create service nodeport for the front voting app, you can use the default service cluster ip  for  other internal pods of voting app except worker node.

===================================================================================================================================
