# Setup

## Add new worker node

```bash
curl -sfL https://get.k3s.io | K3S_URL=https://192.168.10.2:6443 K3S_TOKEN='xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' K3S_NODE_NAME='k3s-worker' INSTALL_K3S_VERSION='v1.26.3+k3s1' sh -
```
