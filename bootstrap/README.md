# Bootstrap instructions

This directory contains the minimal manifest setup to bootstrap [FluxCD](https://fluxcd.io/) on my single-node [Odroid N2+](https://www.hardkernel.com/shop/odroid-n2-with-4gbyte-ram-2/) cluster, powered by [KubeSolo](https://www.kubesolo.io/).

## Setup Instructions

### Preparing the host

```bash
sudo apt install git curl wget unzip htop net-tools libsqlite3-dev iptables sudo bash vim -y
curl -sfL https://get.kubesolo.io | sudo sh -
```

### Bootstrapping Flux

```bash
kubectl apply -k ./
kubectl -n flux-system create secret generic sops-age --from-file ~/.config/sops/age/keys.txt
```
