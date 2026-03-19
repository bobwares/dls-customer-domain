# Customer UI DSL Example

## Purpose

This example shows a normalized multi-file specification where:

- **UI form state** lives in a UI model file
- **API request/response contracts** live in an API model file
- **Persisted storage shape** lives in a persistence model file
- **UI pages** reference the UI model and lookups
- **Backend endpoint definitions** reference API models and mapper files
- **Mappers** define transformations between layers

## Structure

```text
customer-ui-dsl-example/
  README.md
  models/
    ui/
      customer-form.model.yaml
    api/
      customer-api.model.yaml
    persistence/
      customer.persistence.model.yaml
  lookups/
    countries.lookup.yaml
    us-states.lookup.yaml
  ui/
    pages/
      customer-create.page.yaml
      customer-edit.page.yaml
  backend/
    customer.backend.yaml
  mappers/
    customer-form-to-api.mapper.yaml
    customer-api-to-persistence.mapper.yaml
    customer-persistence-to-api.mapper.yaml
```

## Reference Convention

Files use simple relative file references, for example:

- `../../models/ui/customer-form.model.yaml#/models/CustomerForm`
- `../models/api/customer-api.model.yaml#/models/CreateCustomerRequest`

## Design Notes

### UI Model

The UI model contains **form state** only. It includes UI-only fields like:

- `sameAsHomeAddress`

### API Model

The API model contains **transport contracts** only. It does not include UI-only helper fields.

### Persistence Model

The persistence model contains **stored records** and storage metadata only.

### Mappers

Mappers make transformations explicit so the system does not have to guess how one layer maps to another.
