2026-03-23 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# gRPC

## What is it?
gRPC is a high-performance, open-source framework developed by Google that enables communication between services in a distributed system. It uses HTTP/2 for transport and Protocol Buffers (protobuf) as its interface definition language, allowing services to communicate with each other in a language-agnostic way.

## Why does it matter?
In today's software engineering landscape, microservices architectures are increasingly popular. gRPC facilitates efficient and reliable communication between these services, providing features like streaming, authentication, and load balancing. Its ability to work across multiple programming languages makes it a powerful tool for developers building scalable applications.

## Example
Here's a simple example of a gRPC service definition in a `.proto` file, which describes a service that greets users:

```proto
syntax = "proto3";

service Greeter {
  rpc SayHello (HelloRequest) returns (HelloResponse);
}

message HelloRequest {
  string name = 1;
}

message HelloResponse {
  string message = 1;
}
```

In this example, the `Greeter` service has a method `SayHello`, which takes a `HelloRequest` and returns a `HelloResponse`. When implemented, this can be used to create a simple API that greets users by their name!