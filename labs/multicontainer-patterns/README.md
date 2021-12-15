# Multi-Container Pod Design Patterns in Kubernetes

## Init containers
Init containers help us separate the application logic from its startup procedure, such as seeding a database

In this example, we use an init container to retreive the html that will be served by by httpd web server.


## Sidecar pattern
A sidecar is just a container that runs on the same Pod as the application container. Because it shares the same volume and network as the main container, it's able to extend and enhance the functionality of the main container without changing it.

In this example, we use a sidecard to periodically retreive the html that is served by httpd web server

## Ambassador pattern

Ambassador pattern often acts as a proxy to decouple the main Pod from its external dependencies.

## Adapter pattern

Use a sidecar to provide a unified interface for our application container that can be used by a third-party service (in this case prometheus)

In this example, we use `nginx-prometheus-exporter` to make Nginx metrics available  to prometheus