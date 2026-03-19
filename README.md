# Customer Domain

DSL-driven customer domain specification using the app-dsl format for code generation.

## Overview

This project defines a complete customer domain using declarative YAML specifications. The DSL separates concerns across UI, API, and persistence layers with explicit mappers for transformations.

## Structure

```
customer-domain/
  app-dsl/
    models/
      ui/                    # Form state models
      api/                   # API request/response contracts
      persistence/           # Database record shapes
    mappers/                 # Layer transformation definitions
    lookups/                 # Reference data (countries, states)
    ui/pages/                # Page definitions
    backend/                 # Endpoint specifications
  ai/agentic-pipeline/       # Turn tracking artifacts
```

## Models

| Layer       | File                              | Purpose                    |
|-------------|-----------------------------------|----------------------------|
| UI          | `customer-form.model.yaml`        | Form state with validation |
| API         | `customer-api.model.yaml`         | Transport contracts        |
| Persistence | `customer.persistence.model.yaml` | Database record schema     |

## Endpoints

| Endpoint         | Method | Path                  |
|------------------|--------|-----------------------|
| Create Customer  | POST   | `/api/customers`      |
| Get Customer     | GET    | `/api/customers/{id}` |
| Update Customer  | PUT    | `/api/customers/{id}` |

## Mappers

- `customer-form-to-api.mapper.yaml` — UI form to API request
- `customer-api-to-persistence.mapper.yaml` — API request to database record
- `customer-persistence-to-api.mapper.yaml` — Database record to API response

## Lookups

- `countries.lookup.yaml` — Country codes and names
- `us-states.lookup.yaml` — US state codes and names

## Usage

These DSL specifications are consumed by code generators to produce:
- React form components
- NestJS/Express API controllers
- Prisma/TypeORM entities
- Validation logic
- Type definitions

## License

Proprietary
