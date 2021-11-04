## Stages =>

* 1. Download minikube

* 2.  Start Minikube

* 3. Create a secret containing the OpenLDAP users and passwords that your deployments will use by running the command below.

    -- kubectl create secret generic openldap --from-literal=adminpassword=123456 --from-literal=users=shachar,gil --from-literal=passwords=shachar,gil

* 4. Create Deployment.

   -- kubectl create -f deployment.yaml
   -- kubectl create -f svc.yaml  

* 5. Deploy the MariaDB Galera cluster with LDAP authentication enabled.

    -- helm repo add demo https://charts.app-catalog.vmware.com/demo
    -- helm install -f values.yaml my-release demo/mariadb-galera

# See <a href="https://docs.bitnami.com/tutorials/create-openldap-server-kubernetes/"> Guide </a>