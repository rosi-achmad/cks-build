# cks-build
Build Cloudstack Kubernetes Service ISO  

# Eg: To generate the latest kubernetes iso

1.27.2,		kubernetes version, see https://github.com/kubernetes/kubernetes/releases  
1.3.0,		CNI version, see https://github.com/containernetworking/plugins/releases  
1.27.0,		cri-tools version, see https://github.com/kubernetes-sigs/cri-tools/releases  
1.11,			weave addon for kubernetes, see https://github.com/weaveworks/weave/tree/master/prog/weave-kube  
2.7.0,		kubernetes dashboard version, see https://github.com/kubernetes/dashboard/release

# Usage:  
./create-kubernetes-binaries-iso.sh OUTPUT_PATH KUBERNETES_VERSION CNI_VERSION CRICTL_VERSION WEAVENET_NETWORK_YAML_CONFIG DASHBOARD_YAML_CONFIG [OPTIONAL_OUTPUT_FILENAME]

# Example:  
CNI using Calico:  
./create-kubernetes-binaries-iso.sh ./ 1.32.0 1.6.2 1.32.0 https://raw.githubusercontent.com/projectcalico/calico/v3.29.1/manifests/calico.yaml https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml setup-v1.32.0  

CNI using CILIUM:  
./create-kubernetes-binaries-iso.sh ./ 1.32.0 1.6.2 1.32.0 http://127.0.0.1:8080/cilium-install.yaml https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml setup-v1.32.0-cilium
