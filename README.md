# Containerized Rust Actix Web App

## Overview

This repository contains the instructions and sample project for containerizing a simple ``Rust`` ``Actix`` Web application using ``Docker``.

## Prerequisites

The following software is required to be installed on your system:
1. [Rust](https://www.rust-lang.org/tools/install)
2. [Docker](https://docs.docker.com/get-docker/)

## Instructions

### A. Rust Actix Web Application

1. create a new rust project using the following command, and go to the project directory:
```bash
cargo new <project_name>
```

2. Add actix-web dependency to the project's ``Cargo.toml``file using the following command:
```bash
cargo add actix-web
```

3. Modify the code in the main.rs file to create a simple actix web server as per requirement.
The code in this repository displays a simple text message.

4. Build the project using the following command:
```bash
cargo build
```

5. Run the project using the following command:
```bash
cargo run
```

6. Open a web browser and navigate to [http://localhost:8080](http://localhost:8080) to verify the application is running as expected.  
**Note**: The port number may vary based on the port number specified in the code.

7. Stop the application by pressing ``Ctrl+C`` in the terminal.

### B. Dockerize the Rust Actix Web Application
1. Create a new file named ``Dockerfile`` in the project root directory with the following contents:
- installing rust
- setting up the working directory
- copying the source code to the working directory
- building the project
- exposing the port
- running the application

Refer to the ``Dockerfile`` in this repository for the sample code.

2. Build the docker image using the following command:
```bash
docker build -t <user_name>/<image_name> . --no-cache
```
**Note**: --no-cache is an optional argument and is used to build the image from scratch

3. Run the docker container using the following command:
```bash
docker run -p 8080:8080 <user_name>/<image_name>
```
**Note**: The port number may vary based on the port number specified in the code.

4. Open a web browser and navigate to [http://localhost:8080](http://localhost:8080) to verify the application is running as expected.

5. Stop the container using the following command:
```bash
docker stop <container_id>
```
**Note**: The container_id can be obtained using the following command:
```bash
docker ps
```

## C. Sample Execution

1. 