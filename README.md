# GRPC Based API Gateway

This project is a Node.js application for building gRPC-based applications and creating web applications using Express.

## Dependencies

The project relies on the following dependencies:

@grpc/grpc-js: A library for building gRPC-based applications.
@grpc/proto-loader: A module for loading Protocol Buffer definitions for gRPC.
express: A web application framework for Node.js.

## Scripts

The project provides the following scripts:

start-recipe: Executes the main.js file inside the ./recipe directory.
start-processor: Executes the main.js file inside the ./processor directory.
start: Concurrently runs both the recipe/main.js and processor/main.js files.

## Development Dependencies

The project includes the following development dependency:

concurrently: A utility to run multiple commands concurrently.
Please refer to the documentation or source code for more information on how to use and develop this project.

## Express Gateway using GRPC Web (main Folder)

This code snippet represents a Node.js server application that handles recipe processing using gRPC and provides a RESTful API. It utilizes the following dependencies:

path: A built-in Node.js module for handling file paths.
grpc: A library for working with gRPC in Node.js.
@grpc/proto-loader: A module for loading Protocol Buffer definitions for gRPC.
express: A web application framework for Node.js.
The server sets up gRPC connections to two separate services, Recipes and Processing, defined by Protocol Buffer files (recipes.proto and processing.proto). The Protocol Buffer files are loaded using protoLoader and the loaded package definitions are used to create gRPC stubs for communication with the services.

The server also creates an Express application and sets up routes to handle RESTful API requests. It listens on port 5000 for incoming requests.

The server maintains an in-memory orders object to store order details and status. When a new order is received via a POST request to /orders/:id, the server processes the order asynchronously. It retrieves the recipe associated with the order using the Recipes service, and then initiates processing using the Processing service. The status updates received during the processing are stored in the orders object.

A GET request to /orders/:id retrieves the details of a specific order from the orders object and returns the response.

Please note that the Protocol Buffer files and their respective services should be implemented and running in order for this server to function correctly.

To start the server, execute the command node <filename>.js in the terminal, replacing <filename> with the actual name of the file.

The server will print a message indicating that the RESTful API is listening on port 5000.

## Processor Folder

This code represents a gRPC server written in Node.js. It uses the @grpc/grpc-js library for handling gRPC communication and @grpc/proto-loader for loading Protocol Buffer definitions.

This code sets up a gRPC server that listens on the address 0.0.0.0:50052. It loads the Protocol Buffer definition file processing.proto and creates a gRPC server instance. The process function handles incoming requests and performs some asynchronous operations with a delay. The server is then bound and started.

## recipe Folder

This code snippet demonstrates a gRPC server implementation for a recipe service. It utilizes the @grpc/grpc-js and @grpc/proto-loader packages for handling gRPC functionality.

The server will start and bind to the specified address (0.0.0.0:50051) to accept incoming gRPC requests.

Feel free to modify the code and proto file according to your specific requirements for a recipe service.
