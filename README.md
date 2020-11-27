# bigbang
bigbang k8s platform work-step 

* Step1 - Metallb
 1) step for use Loadbalancer on Baremetal infrastructure
 2) download & install (Manifest) # 현재 기준 0.9.5버전이 최신릴리즈
    kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/namespace.yaml
    kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/metallb.yaml
    kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"
    
* Step2 - Helm3
 1) curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
 2) chmod 700 get_helm.sh
 3) ./get_helm.sh

* Step3 - Rook Ceph



* Step4 - Prometheus + Grafana (Using Helm)

 
