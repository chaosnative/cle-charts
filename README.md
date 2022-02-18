# Helm Charts ChaosNative Litmus Enterprise
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fchaosnative%2Fcle-charts.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fchaosnative%2Fcle-charts?ref=badge_shield)


## Usage

### Pre-Requisites

- Install [helm3](https://helm.sh/docs/intro/install/)
- Kubernetes >= 1.17

### Installation Steps

The following steps will help you install CLE via helm.

#### Step-1: Add the litmus helm repository

```bash
helm repo add chaosnative https://charts.chaosnative.com

helm repo list
```

Output:
```
NAME            URL
chaosnative     https://charts.chaosnative.com                                                               
```

#### Step-2: Create the litmus namespace

```bash
kubectl create ns litmus
```

#### Step-3: Install the litmus chaos center

```bash
helm install -n litmus chaosnative chaosnative/cle
```

Output:
```bash
NAME: chaosnative
LAST DEPLOYED: Mon Dec  6 01:43:14 2021
NAMESPACE: litmus
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
Thank you for installing cle 😀

Your release is named chaosnative and it's installed to namespace: litmus.

Visit https://chaosnative.com to find more info.
```


#### Step-3: Uninstall the ChaosNative Litmus Enterprise

```bash
helm uninstall chaosnative --namespace=litmus
```

Output:
```bash
release "chaosnative" uninstalled
```

---


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fchaosnative%2Fcle-charts.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fchaosnative%2Fcle-charts?ref=badge_large)