gen-cal:
	protoc --go_out=paths=source_relative:. --go-grpc_out=paths=source_relative:. calculator/calculator.proto
run-server:
	go run server/server.go
run-client:
	go run client/client.go