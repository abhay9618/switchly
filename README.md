# Switchly

Switchly is a Java and Spring Boot project for managing organizations, projects, and feature flags through a REST API.

## Repository layout

- [`switchly-api/switchly-api`](switchly-api/switchly-api) — the feature-flag API, using in-memory storage.
- [`api/api`](api/api) — a separate Spring Boot starter project.

## Requirements

- Java 21
- Maven (to build and run `switchly-api`)

## Run the feature-flag API

From the repository root:

```shell
cd switchly-api/switchly-api
mvn spring-boot:run
```

The API starts at `http://localhost:8080`. Data is held in memory and is reset when the application restarts.

## API endpoints

All endpoints are under `/api/v1`.

| Method | Path | Description |
|---|---|---|
| `POST` | `/orgs` | Create an organization |
| `GET` | `/orgs` | List organizations |
| `GET` | `/orgs/{orgId}` | Get an organization |
| `POST` | `/orgs/{orgId}/projects` | Create a project |
| `GET` | `/orgs/{orgId}/projects` | List an organization's projects |
| `GET` | `/projects/{projectId}` | Get a project |
| `POST` | `/projects/{projectId}/flags` | Create a feature flag |
| `GET` | `/projects/{projectId}/flags` | List a project's feature flags |
| `GET` | `/flags/{flagId}` | Get a feature flag |
| `PUT` | `/flags/{flagId}/state` | Update a feature flag's enabled state |
| `DELETE` | `/flags/{flagId}` | Delete a feature flag |

## Tests

Run the feature-flag API tests from its project directory:

```shell
mvn test
```
