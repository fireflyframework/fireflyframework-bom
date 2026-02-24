# Firefly Framework - Bill of Materials (BOM)

[![CI](https://github.com/fireflyframework/fireflyframework-bom/actions/workflows/ci.yml/badge.svg)](https://github.com/fireflyframework/fireflyframework-bom/actions/workflows/ci.yml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Java](https://img.shields.io/badge/Java-21%2B-orange.svg)](https://openjdk.org)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green.svg)](https://spring.io/projects/spring-boot)

> Bill of Materials for the Firefly Framework ensuring consistent, compatible versions across all framework modules.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Configuration](#configuration)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [License](#license)

## Overview

The Firefly Framework BOM (Bill of Materials) provides centralized version management for all Firefly Framework modules. By importing this BOM into your project's `dependencyManagement` section, you ensure that every framework dependency resolves to a compatible, tested version without requiring explicit version declarations.

This is the recommended approach when your project already has its own parent POM and cannot inherit from `fireflyframework-parent`. The BOM covers all core modules, application layers, ECM adapters, IDP implementations, notification providers, rule engine components, webhooks, callbacks, and the config server.

## Features

- Single import provides version management for all Firefly Framework modules
- Covers core framework modules (cache, EDA, CQRS, event sourcing, orchestration engine)
- Covers application layers (application, backoffice, web, domain, data)
- Covers ECM modules and storage adapters (AWS S3, Azure Blob)
- Covers IDP modules (Keycloak, AWS Cognito, internal DB)
- Covers notification providers and core
- Covers rule engine, workflow, webhooks, callbacks, and plugins
- Covers config server
- Compatible with any parent POM

## Requirements

- Java 21+
- Maven 3.9+

## Installation

Import the BOM in your project's `dependencyManagement` section:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.fireflyframework</groupId>
            <artifactId>fireflyframework-bom</artifactId>
            <version>26.02.07</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

## Quick Start

After importing the BOM, add any Firefly Framework module without specifying a version:

```xml
<dependencies>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-starter-core</artifactId>
    </dependency>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.fireflyframework</groupId>
        <artifactId>fireflyframework-eda</artifactId>
    </dependency>
</dependencies>
```

## Configuration

No configuration is required. The BOM is a version-management-only artifact with no runtime behavior.

## Documentation

No additional documentation available for this project.

## Contributing

Contributions are welcome. Please read the [CONTRIBUTING.md](CONTRIBUTING.md) guide for details on our code of conduct, development process, and how to submit pull requests.

## License

Copyright 2024-2026 Firefly Software Solutions Inc.

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.
