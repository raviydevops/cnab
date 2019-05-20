# CNAB bundle for mario game application

cnab spec is used to bundle the application

## Prerequsites

``` no-highlight
Docker
kubernetes cluster config
helm chart
```

## Installing the bundle

Use the following command to install the bundle:

``` bash
docker run -it -v ~/.aws:/root/.aws -v ~/.kube:/root/.kube raviydevops/cnab_invovation_image:latest install
```

## Uninstalling the bundle

Use the following command to uninstall the bundle:

``` bash
docker run -it -v ~/.aws:/root/.aws -v ~/.kube:/root/.kube raviydevops/cnab_invovation_image:latest uninstall
```

## Status of the bundle

Use the following command to know the status the bundle:

``` bash
docker run -it -v ~/.aws:/root/.aws -v ~/.kube:/root/.kube raviydevops/cnab_invovation_image:latest status
```
