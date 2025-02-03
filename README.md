# cks-build
Build Kubernetes ISO for Cloudstack

# Prequisite
Tested using ubuntu 24.04. Just run command:  
```shell
sudo apt install genisoimage  
sudo curl https://raw.githubusercontent.com/rosi-achmad/cks-build/refs/heads/main/install-docker.sh | sh  
sudo curl https://raw.githubusercontent.com/rosi-achmad/cks-build/refs/heads/main/create-kubernetes-binaries-iso.sh -o create-kubernetes-binaries-iso.sh && sudo chmod +x create-kubernetes-binaries-iso.sh
```

# Eg: To generate the latest kubernetes iso

1.27.2,		kubernetes version, see https://github.com/kubernetes/kubernetes/releases  
1.3.0,		CNI version, see https://github.com/containernetworking/plugins/releases  
1.27.0,		cri-tools version, see https://github.com/kubernetes-sigs/cri-tools/releases  
1.11,			weave addon for kubernetes, see https://github.com/weaveworks/weave/tree/master/prog/weave-kube  
2.7.0,		kubernetes dashboard version, see https://github.com/kubernetes/dashboard/release

# Usage:  
```shell
./create-kubernetes-binaries-iso.sh OUTPUT_PATH KUBERNETES_VERSION CNI_VERSION CRICTL_VERSION NETWORK_YAML_CONFIG DASHBOARD_YAML_CONFIG [OPTIONAL_OUTPUT_FILENAME]
```

# Example:  
CNI using Calico:
```shell
./create-kubernetes-binaries-iso.sh ./ 1.32.1 1.6.2 1.32.0 https://raw.githubusercontent.com/projectcalico/calico/v3.29.1/manifests/calico.yaml https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml setup-v1.32.1-calico  
```

CNI using Cilium:
```shell
./create-kubernetes-binaries-iso.sh ./ 1.32.1 1.6.2 1.32.0 https://raw.githubusercontent.com/rosi-achmad/cks-build/refs/heads/main/cilium-install.yaml https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml setup-v1.32.1-cilium
```
