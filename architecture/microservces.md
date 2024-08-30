# Microservices Architecutre

## Definition (From [Microsoft](https://learn.microsoft.com/en-us/training/modules/dotnet-microservices/2-what-are-microservices))

A microservices architecture is when a large (usually a monolithic 
application) is split up into a set of smaller services. Each service
runs in its own process and communicates with other processes by using 
protocols like HTTP/HTTPs, WebSocket, or Advanced Message Queuing 
Protocol (AMQP). Each microservice implements a specific, end-to-end domain
business capabulity within a certain context boundary. Rach microservice must be developed
autonomously and must be independently deployable. Finally, each microservice should own
its related domain data model and domain logic. Microservices can be based on different data
storage technologies and different programming languages.