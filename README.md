## A simple containerized project running in PostgreSQL and Odoo

### This project is implemented in single node, minikube cluster

I used minikube environment to run this project. As is mentioned in docker hub, port 8069 is used for odoo, and 5432 is used for Postgresql. To share the data between the pods, folder `/var/lib/odoo` is mounted among the pods.

### Installation and Usage Instructions

To install the odoo and the Postgresql database, apply the yaml files and services included in this repo. The command used to apply the yaml files should be entered in kubernetes environment as an example below:

`kubectl apply -f odoo.yaml`

### Extra Tasks

The following tasks will be pushed to this repository soon.

- The database is backed up nightly to Amazon S3 (or another S3 compatible object storage)
- The Kubernetes manifests are a part of a Helm chart.
- Introduce any form of delivery pipeline using any CI/CD of your choice.
