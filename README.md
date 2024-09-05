# gRPC Golang Example

This repository contains three gRPC examples in Go:

- **helloworld**: Simple gRPC
- **routeguide**: Route guide with gRPC
- **calculator**: Calculator with gRPC

## Prerequisites

Before running the examples, ensure you have the following installed:

1. **Install Go (latest two major releases)**:  
   Follow the instructions in the [Go’s Getting Started guide](https://golang.org/doc/install).

2. **Install Protocol Buffer Compiler (`protoc`) version 3**:  
   Install the protocol buffer compiler following the instructions from the [Protocol Buffer Compiler Installation guide](https://grpc.io/docs/protoc-installation/).

3. **Install Go plugins for Protocol Buffer Compiler**:  
   You can install the necessary Go plugins for gRPC and set the PATH with the following commands:

   ```bash
   # Install the Protocol Buffer compiler plugins for Go
   go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
   go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

   # Update your PATH to include the installed Go binaries
   export PATH="$PATH:$(go env GOPATH)/bin"
   ```

## Usage

Every example have each folder and need to cd before running script in Makefile

`cd ./folder`

```makefile
# Generate Protobuf files for calculator example
gen-cal:
	protoc --go_out=paths=source_relative:. --go-grpc_out=paths=source_relative:. calculator/calculator.proto

# Run the gRPC server
run-server:
	go run server/server.go

# Run the gRPC client
run-client:
	go run client/client.go
```

For running these command:

- Gen proto file: `make gen-cal`
- Run server: `make run-server`
- Run client: `make run-client`
