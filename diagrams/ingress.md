```puml
@startuml

node "Client" as client

node "Kubernetes Cluster" {
    node "Ingress" as ingress
    component "Service 1" as serviceA
    component "Service 2" as serviceB
    node "Node 1" as node1 {
        component "Pod 1 - 1" as pod11
        component "Pod 2 - 1" as pod21           
        component "Pod 2 - 3" as pod23
    }
    node "Node 2" as node2 {
        component "Pod 1 - 2" as pod12
        component "Pod 2 - 2" as pod22
    }
}

client -> ingress
ingress --> serviceA : service1.example.com
ingress --> serviceB : service2.example.com
serviceA --> pod11
serviceA --> pod12
serviceB --> pod21
serviceB --> pod22
serviceB --> pod23

@enduml
```