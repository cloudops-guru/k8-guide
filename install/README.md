# k8-guide

Kuberntes Installation is in three steps

# Step 1 : Install docker, Kubeadmin , kubelet and kubectl in both master nodes and slave nodes

You can perform this operation by by running following script 

sh ./k8-install-ubuntu.sh  "Kubernetes-version"

sh ./k8-install-ubuntu.sh "1.18.5-00"

# Step2 : Init Kubeadmin in master and setup Network 
Run following commands in master node to init and setup CNI , Scroll and Copy kube admin join comamnds for Next step

./k8-master-init-nw.sh

# Step3 : Join the master

Run the join commands from worker node with sudo 

Ex : sudo kubeadm join 10.0.1.101:6443 --token token-dummy \
    --discovery-token-ca-cert-hash sha256:12b14f68b4300f51ace8c0b85ad7b35b906253dd_this_is_an_example


Move to Master node and run `kubectl get nodes` to see the status of the nodes

