# kubernetes_minkube

Kubernetes project to run on Minikube.

## Table of Contents

- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [License](#license)

## Requirements

- [kubectl >= v1.20.4](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [minikube >= v1.18.0](https://minikube.sigs.k8s.io/docs/start/)

## Setup

1. Set up Minikube

```sh
minikube start
```

2. Apply Secret

```sh
kubectl apply -f k8s-config/secret
```

3. Set up MongoDB

```sh
kubectl apply -f k8s-config/deployment/mongo.yml && kubectl apply -f k8s-config/service/mongo.yml
```

4. Apply ConfigMap

```sh
kubectl apply -f k8s-config/configmap
```

5. Set up Express app

```sh
kubectl apply -f k8s-config/deployment/express.yml && kubectl apply -f k8s-config/service/express.yml
```

## Usage

### Assign an External IP to the express-service

```sh
minikube service express-service
```

## License

**kubernetes_minkube** is licensed under [MIT](./LICENSE).
