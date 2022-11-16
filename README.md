## A simple containerized project running in PostgreSQL and Odoo

### This project is implemented in single node, minikube cluster

I used minikube environment to run this project. As is mentioned in docker hub, port 8069 is used for odoo, and 5432 is used for Postgresql. To share the data between the pods, folder `/var/lib/odoo` is mounted among the pods.

### Installation and Usage Instructions

To run the odoo and the postgresql database, apply all the yaml files and services included in this repo. The command used to apply the yaml files should be entered in kubernetes environment as an example below:

`kubectl apply -f odoo.yaml`

After applying all the yaml files, you will have access to odoo container entering `127.0.0.1:8069`, if the http connection could not be established, you need to forward the specified port to another port running the command below:

`kubectl port-forward svc/odooservice 8080:8069`

### Extra Tasks

The following tasks will be pushed to this repository soon.

- The database is backed up nightly to Amazon S3 (or another S3 compatible object storage)
- The Kubernetes manifests are a part of a Helm chart.
- Introduce any form of delivery pipeline using any CI/CD of your choice.
