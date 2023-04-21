# Purpose
This repository holds all the supporting [Helm](https://helm.sh/) charts and [ArgoCD](https://github.com/argoproj/argo-cd) [Application Templates](https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/application.yaml) to bootstrap a Kubenetes cluster and allow for easier day two operations. 

# Repository Layout Explaination
```
├── charts - Directory for defining charts you want to install through ArgoCD
│   └── aws-pca-issuer - Name of Chart
│       ├── templates - Directory that holds user created helm templates that should be bundled with the chart install
│       ├── Chart.yaml - Defines what repo to helm install from, name, and helm chart version
│       └── values.yaml - Global helm values that you would want set regardless of enviroment
└── applications - Directory for holding all available services that can be installed in the cluster
    ├── Chart.yaml - Contains the name of the App-of-Apps deployment in this case infra
    ├── templates - Directory that containers the templates that define Applications to ArgoCD
    │   └── *.yaml - The Application Templates that tells ArgoCD what to deploy and from where
    └── values.yaml - Globally shared values that all clusters would want, cluster specific services are passed in through terraform
```
