* Install podman for windows. I prefer using [scoop](https://scoop.sh/).
```
scoop install podman
```
* Initialize a podman machine for minikube
```
podman machine init minikube
```
* Set rootful for this podman machine
```
podman machine set --rootful minikube
```
* Start this podman machine
```
podman machine start minikube 
```
* Start minikube with podman driver and cri-o container runtime
```
minikube start --driver=podman --container-runtime=cri-o  
```
* Follow the instruction from above step to verify minikube status
```
minikube kubectl -- get pods -A
```
* record
```
PS C:\Users\Lance> podman machine init minikube
Extracting compressed file
Importing operating system into WSL (this may take a few minutes on a new WSL install)...
正在匯入，這可能需要幾分鐘的時間。   
操作順利完成。
Configuring system...
Generating public/private ed25519 key pair.
Your identification has been saved in minikube
Your public key has been saved in minikube.pub
The key fingerprint is:
SHA256:WYKgh5D9rqke8V5A5/qLwYGw2twlbagFyY8qmfw2A64 root@Lan2023
The key's randomart image is:
+--[ED25519 256]--+
|.o  .            |
|.o.+ . .         |
|. *o... . .      |
|..o=+o   +       |
|.o.+=.+ S        |
|oB++=+           |
|Bo=B..           |
|..*+=            |
|Eo.+oo.          |
+----[SHA256]-----+
Machine init complete
To start your machine run:

        podman machine start minikube

PS C:\Users\Lance> podman machine set --rootful minikube                                                                                                                                                              
PS C:\Users\Lance> podman machine start minikube                                                                                                                                                                      
Starting machine "minikube"
API forwarding listening on: npipe:////./pipe/docker_engine

Docker API clients default to this address. You do not need to set DOCKER_HOST.
Machine "minikube" started successfully
PS C:\Users\Lance> minikube start --driver=podman --container-runtime=cri-o                                                                                                                                           
* minikube v1.30.1 on Microsoft Windows 11 Pro 10.0.22621.1555 Build 22621.1555
* Using the podman (experimental) driver based on user configuration
* Using Podman driver with root privileges
* Starting control plane node minikube in cluster minikube
* Pulling base image ...
E0416 08:24:47.593114   22332 cache.go:188] Error downloading kic artifacts:  not yet implemented, see issue #8426
* Creating podman container (CPUs=2, Memory=32700MB) ...
* Preparing Kubernetes v1.26.3 on CRI-O 1.24.4 ...
E0416 08:25:35.098566   22332 start.go:131] Unable to get host IP: RoutableHostIPFromInside is currently only implemented for linux
  - Generating certificates and keys ...
  - Booting up control plane ...
  - Configuring RBAC rules ...
* Configuring CNI (Container Networking Interface) ...
  - Using image gcr.io/k8s-minikube/storage-provisioner:v5
* Verifying Kubernetes components...
* Enabled addons: storage-provisioner, default-storageclass
* kubectl not found. If you need it, try: 'minikube kubectl -- get pods -A'
* Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
PS C:\Users\Lance> minikube kubectl -- get pods -A                                                                                                                                                                    
    > kubectl.exe.sha256:  64 B / 64 B [---------------------] 100.00% ? p/s 0s
    > kubectl.exe:  46.49 MiB / 46.49 MiB [--------] 100.00% 13.37 MiB p/s 3.7s
NAMESPACE     NAME                               READY   STATUS    RESTARTS   AGE
kube-system   coredns-787d4945fb-trt64           1/1     Running   0          46s
kube-system   etcd-minikube                      1/1     Running   0          60s
kube-system   kindnet-qks84                      1/1     Running   0          46s
kube-system   kube-apiserver-minikube            1/1     Running   0          60s
kube-system   kube-controller-manager-minikube   1/1     Running   0          60s
kube-system   kube-proxy-9jk7v                   1/1     Running   0          46s
kube-system   kube-scheduler-minikube            1/1     Running   0          59s
kube-system   storage-provisioner                1/1     Running   0          57s
PS C:\Users\Lance> 
```