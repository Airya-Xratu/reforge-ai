# Architecture Report

## Overview

| Field | Value |
|---|---|
| Pattern | |
| State Management | |
| DI Framework | |
| Navigation | |
| Networking | |
| Persistence | |
| Confidence | HIGH / MEDIUM / LOW |

## Module Map

```
module_a
├── depends on → module_b
├── depends on → shared
└── exports → [public API]

module_b
├── depends on → shared
└── exports → [public API]

shared
└── exports → [public API]
```

## Dependency Graph Issues

| Issue | Description | Severity |
|---|---|---|
| circular | | |
| god_module | | |
| orphan | | |
| violation | | |

## State Management

| Store/Bloc/Provider | State Fields | Consumers | Scope |
|---|---|---|---|
| | | | |

## Networking

| Property | Value |
|---|---|
| Client | |
| Base URL Config | |
| Interceptors | |
| Auth Header | |
| Error Handling | |
| Retry Logic | |

### API Endpoints

| Method | Path | Purpose | Auth | Pagination |
|---|---|---|---|---|
| | | | | |

## Persistence

| Property | Value |
|---|---|
| Local DB | |
| Caching | |
| Offline Support | |
| Encryption | |

## Authentication

| Property | Value |
|---|---|
| Type | |
| Storage | |
| Refresh | |
| Biometric | |

## DI Configuration

| Property | Value |
|---|---|
| Framework | |
| Scope | |
| Registration | |

## Testing

| Level | Present | Coverage | Notes |
|---|---|---|---|
| Unit | | | |
| Widget | | | |
| Integration | | | |
| E2E | | | |

## CI/CD

| Property | Value |
|---|---|
| Provider | |
| Stages | |
| Environments | |

## Technical Debt

| Item | Location | Impact | Priority |
|---|---|---|---|
| | | | |

## Architectural Risks

| Risk | Impact | Likelihood | Mitigation |
|---|---|---|---|
| | | | |
