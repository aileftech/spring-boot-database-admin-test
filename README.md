# SnapAdmin Test Projects

This repo contains multiple [SnapAdmin](https://github.com/aileftech/snap-admin)-related projects. 

Each folder contains a project consisting of a Spring Boot + SnapAdmin application, which serves a dual purpose:

 * **Documentation**: the sample code is documented and can be used as a reference to show how to
   implement specific features/behaviours of SnapAdmin;
 * **Testing**: if applicable, each project also contains tests related to the specific focus of the project

At the moment, these are the available projects:

* main: The main SnapAdmin project which shows how to use most of the features and also contains
most of the tests. Also used to power the live demo.

* auth: A sample SnapAdmin projects which includes the implementation of a Spring Security
configuration to protect SnapAdmin with authentication/authorization.


## How to run

The following procedure can be used to run any individual project. Each project has its own README as well
where additional information is available, if necessary.

### 📋 Prerequisites
Before you begin, please ensure that you have the following software and tools installed:

#### [Apache Maven](https://maven.apache.org/download.cgi)
Apache Maven is a powerful project management and build automation tool. It is used for building and managing Java projects, including this one.

#### [Docker](https://www.docker.com)
It's not mandatory to have Docker installed, but for ease of use we provide a docker-compose file that will start a MySQL instance. If you don't want
to use Docker, you will need to customize the `application.properties` file in order to connect to your own database. 


### 🛠️ Run the Program

  - Clone the Repository.

    ```sh
    git clone https://github.com/aileftech/snap-admin-test
    ```
  - Navigate to the project folder inside the repo, e.g. 'auth'

    ```sh
    cd snap-admin-test/auth
    ```
  - Create & Run Docker Container: 
        
    ```sh
    docker-compose -f docker-compose.yaml up
    ```

    If you decided not to use Docker, check the `src/main/resources/application.properties` file and configure the datasource properly. You can also use an H2
    embedded database which doesn't require starting a server.

  - Run the following command in the terminal: 

    ```sh
    mvn spring-boot:run or 'mvn spring-boot:start' to run in background.
    ```

### 🖥️ Accessing Admin Panel

Once the application is up and running, you can access the admin interface by opening your web browser and navigating to the following URL:

[http://localhost:8080/admin](http://localhost:8080/admin)


### 📝 Tests

To execute the project-specific tests, run the following command inside the project's directory. Make sure the project application is already running
in the background.

```shell
mvn test
```

Also make sure you are running on a "clean" instance of the database, i.e. you have not changed its content. If this is the case, it could
interfere with the correct execution of the tests.
