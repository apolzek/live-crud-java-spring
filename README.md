# Simple CRUD
This repository contains a simple CRUD project built using Java Spring. The aim of this repository is to practice and share how you can build all CRUD Methods using Java Spring.

This project was build during a [live in my Youtube Channel](https://www.youtube.com/watch?v=tP6wtEaCnSI).

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [API Endpoints](#api-endpoints)
- [Database](#database)

## Installation

1. Clone the repository:

```bash
$ git clone https://github.com/Fernanda-Kipper/live-crud-java-spring.git
```

2. Install Java and Maven

```sh
asdf plugin add java
asdf install java graalvm-22.3.0+java19
asdf global java graalvm-22.3.0+java19
tail $HOME/.tool-versions

asdf plugin-add maven 
asdf install maven 3.5.0
asdf global maven 3.5.0
```

3. Database
`docker compose up -d`

4. Install dependencies with Maven
```
mvn install
mvn clean package
```

5. Start the application with Maven
```
java -jar target/crud-0.0.1-SNAPSHOT.war
```

6. The API will be accessible at http://localhost:8080

```
curl --location 'http://localhost:8080/product' \
--header 'Content-Type: application/json' \
--data '{
    "name": "car",
    "price_in_cents": 20000000
}'
```

## API Endpoints
The API provides the following endpoints:

```markdown
GET /product - Retrieve a list of all data.

POST /product - Register a new data.

PUT /product - Alter data.

DELETE /product/{id} - Inactivate data.
```

## Database
The project uses PostgresSQL as the database. The necessary database migrations are managed using Flyway.

To install PostgresSQL locally you can [click here](https://www.postgresql.org/download/).

## Docker

You can run this project with Docker by running the following command:


```bash
$ docker-compose up
```
Run the application and access http://localhost:15432

Enter the email and password configured in [Docker file](./docker-compose.yml).

To install Docker locally you can [click here](https://www.docker.com/products/docker-desktop/).