# Firefly Framework - Bill of Materials (BOM)
    
[![CI](https://github.com/fireflyframework/fireflyframework-bom/actions/workflows/ci.yml/badge.svg)](https://github.com/fireflyframework/fireflyframework-bom/actions/workflows/ci.yml)

A Maven BOM that provides centralized version management for all Firefly Framework modules. Importing this artifact into your `dependencyManagement` section ensures that every framework dependency resolves to a compatible, tested version without requiring explicit version declarations.

## What is a BOM?

A Bill of Materials is a special POM artifact (`<packaging>pom</packaging>`) that declares a set of dependency versions. When imported via `<scope>import</scope>`, it allows your project to omit `<version>` tags on those dependencies while guaranteeing version consistency across the entire dependency tree.

## Usage

Import the BOM in your project's `dependencyManagement` section:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.fireflyframework</groupId>
            <artifactId>fireflyframework-bom</artifactId>
            <version>1.0.0-SNAPSHOT</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Then declare framework dependencies without specifying versions:

```xml
<dependencies>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-eda</artifactId>
    </dependency>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-cqrs</artifactId>
    </dependency>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-cache</artifactId>
    </dependency>
</dependencies>
```

## BOM vs Parent POM

| Approach | When to Use |
|---|---|
| **fireflyframework-parent** | Your project can inherit from the Firefly parent. This gives you both version management and plugin configuration. |
| **fireflyframework-bom** | Your project already has its own parent POM. The BOM provides version alignment only, without imposing build conventions. |

If you inherit from `fireflyframework-parent`, you do not need to import the BOM separately -- the parent already includes all managed versions.

## Managed Artifacts

### Core Framework

| Artifact ID | Description |
|---|---|
| `fireflyframework-core` | Actuator, health indicators, service registry, observability |
| `fireflyframework-domain` | DDD base entities, value objects, aggregate roots |
| `fireflyframework-utils` | Shared utilities and template rendering |
| `fireflyframework-validators` | Annotation-based data validators |
| `fireflyframework-web` | WebFlux exception handling, idempotency, OpenAPI |
| `fireflyframework-client` | Reactive REST, SOAP, gRPC client with resilience |
| `fireflyframework-cache` | Multi-provider caching abstraction |
| `fireflyframework-r2dbc` | Reactive database auto-configuration |

### Distributed Patterns

| Artifact ID | Description |
|---|---|
| `fireflyframework-eda` | Event-Driven Architecture with Kafka/RabbitMQ |
| `fireflyframework-cqrs` | Command Query Responsibility Segregation |
| `fireflyframework-eventsourcing` | Event Sourcing with snapshots and projections |
| `fireflyframework-transactional-engine` | Saga and TCC distributed transactions |
| `fireflyframework-workflow` | Workflow orchestration engine |
| `fireflyframework-data` | Data processing and job orchestration |

### Enterprise Content Management

| Artifact ID | Description |
|---|---|
| `fireflyframework-ecm` | Core ECM abstractions |
| `fireflyframework-ecm-storage-aws` | Amazon S3 storage adapter |
| `fireflyframework-ecm-storage-azure` | Azure Blob Storage adapter |

### Identity Provider

| Artifact ID | Description |
|---|---|
| `fireflyframework-idp` | IDP abstraction layer |
| `fireflyframework-idp-aws-cognito` | AWS Cognito adapter |
| `fireflyframework-idp-internal-db` | Database-backed IDP |
| `fireflyframework-idp-keycloak` | Keycloak adapter |

### Notifications

| Artifact ID | Description |
|---|---|
| `fireflyframework-notifications` | Core notification abstractions |

## License

Apache License 2.0

Copyright 2024-2026 Firefly Software Solutions Inc.