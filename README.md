# bigbang
bigbang k8s platform work-step 

* Step1 - Metallb*
 1) step for use Loadbalancer on Baremetal infrastructure
 2) download & install (Manifest) # 현재 기준 0.9.5버전이 최신릴리즈
    kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/namespace.yaml
    kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/metallb.yaml
    kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"
 
 

