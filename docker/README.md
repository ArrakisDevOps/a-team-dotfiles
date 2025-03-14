# DevOps Helper image

Arrakis DevOps Team Helper Image

- git
- tfswitch (Terrafrom / OpenTofu)
- conda (Python)
- aws-cli

## [tfswitch (Terraform / OpenTofu)](https://tfswitch.warrensbox.com)

TFSwitch is a command-line tool designed to simplify the management of multiple Terraform versions.

### [Usage](https://tfswitch.warrensbox.com/usage/commandline/)
*By deafult use a latest terraform version.*
#### How to download specific version:
```shell
tfswitch 0.13.0
```
*The **-n** menas ehat is your env name*

#### How to list the versions:
```shell
tfswitch
```

#### How to switch Terraform to OpenTofu:
```shell
export TF_PRODUCT=opentofu
tfswitch
```

#### How to switch OpenTofu to Terraform:
```shell
export TF_PRODUCT=terraform
tfswitch
```

## [Conda (Python)](https://www.anaconda.com/docs/main)

### [Usage](https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-python.html)

#### How to create new env:
```shell
conda create -n py39 python=3.9
```
*The **-n** menas ehat is your env name*

#### How to activate env:
```shell
conda activate py39
```

#### How to deactive env:
```shell
conda deactive
```
*Return to the base*

# Plan

We would group components into DevOps toolset categories.

- basic setup like git, editor, shell etc.
- Docker
- Kubernetes
- Public Cloud provider like AWS
- Python dev env
- Go
- AWS
- Azure
and more...

We could even create dev containers for each specific bigger components or an all-in-one if possible.
