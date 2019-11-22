#First step
oc new-project mssql

#Create credentials
oc apply -f secret.yaml
#or
oc create secret generic mssql --from-literal=SA_PASSWORD="Sql2019isfast"

#Create storage
oc apply -f storage.yaml

#Create deplyoment
oc apply -f sqldeployment.yaml

Service is configured as nodePort so you need to setup on your LoadBalancer to forward traffic from port 31433 to all worker nodes
