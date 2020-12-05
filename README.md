# dotnet-docker-integration-test

### Summary
Sample ASP NET Core 5 API using docker-compose to run integration tests. The API is a timesheet system sample that the employee of a company launch worked hours. Developed using [.NET 5](https://dotnet.microsoft.com/download/dotnet/5.0), SqlServer with [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/what-is-new/ef-core-5.0/whatsnew) and [Docker](https://hub.docker.com/_/microsoft-dotnet-core) (containerized SQLServer and .NET 5 SDK).

### Running the project

#### Locally via `dotnet` command line tool

Running the project locally requires initializing the database (SqlServer) on docker.

```
  cd src

  nuget restore

  docker-compose up -d sql-server-database

  dotnet run
```

#### In a docker container via `docker-compose`

Initializes the database (SqlServer) and the Api on docker.

```
  cd src

  docker-compose up timesheets-api
 ```

# Running tests

#### Locally via `dotnet` command line tool

```
  cd src

  docker-compose up -d sql-server-database

  dotnet test ../test/Timesheets.Tests.csproj
```

#### In a docker container via `docker-compose`

```
  cd src

  docker-compose up integration-tests
```