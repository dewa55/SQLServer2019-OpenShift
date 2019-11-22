1. Creating user

oc new-project mssql

2. Create secret

oc apply -f secret.yaml

or

oc create secret generic mssql --from-literal=SA_PASSWORD="Sql2019isfast"

3. Create storage

oc apply -f storage.yaml

4. Create deplyoment

oc apply -f sqldeployment.yaml


Service is configured as nodePort so you need to setup on your LoadBalancer to forward traffic from port 31433 to all worker nodes
