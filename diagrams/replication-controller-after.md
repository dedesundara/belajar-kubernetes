```puml
@startuml
node "Node 1" {
    component "Pod 1" as pod1
    component "..." as pod3
}

node "Node 2" {
    component "Pod 1" as pod2
    component "..." as pod4
}

component "Replication Controller" as rc

rc -up-> pod1
rc -up-> pod2
@enduml
```