```puml
@startuml

node "Client" as client
node "Load Balancer 1" as lb1

node "Kubernetes Cluster" {
    component "Service 1" as service1
    node "Node 1" as node1 {
        component "Pod 1 - 1" as pod11
    }
    node "Node 2" as node2 {
        component "Pod 1 - 2" as pod12
    }
}

client -right-> lb1
lb1 -up-> node1
lb1 -up-> node2
node1 --> service1
node2 --> service1
service1 --> pod11
service1 --> pod12

@enduml
```