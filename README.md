# bigbang
bigbang k8s platform work-step 

* Step1 - Metallb*
- step for use Loadbalancer on Baremetal infrastructure
- Download & Install (Manifest) # 현재 기준 0.9.5버전이 최신릴리즈
   kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/namespace.yaml
   kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.5/manifests/metallb.yaml
   kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"
 
- 참고사항
: 병목현상 생길 가능성 있음 - 특정 노드에 트래픽 집중 및 이후 분산 (layer2 mode)
: annotations를 활용하여 multi address-pool을 지원할 수 있음
 
(ex)
apiVersion: v1
kind: Service
metadata:
  name: nginx
  annotations:
    metallb.universe.tf/address-pool: web   ## 'web' address-pool에서 사용 지정
spec: 
   
