# ADR: Turn T003 - Customer List Page Structure

## Status

Accepted

## Context

The project has create and edit pages for customers but no list page. The backend has listCustomers and deleteCustomer endpoints. A list page is needed to complete the CRUD flow.

## Decision

Create `customer-list.page.yaml` following the established DSL patterns with:
- Data table component bound to customers collection
- Row actions for edit (navigation) and delete (API call with confirmation)
- Pagination, search, and empty state for good UX
- Reference existing backend endpoints

## Consequences

- Completes the customer management UI flow
- Users can view all customers in a searchable, paginated table
- Edit action navigates to existing edit page
- Delete action calls deleteCustomer endpoint with confirmation dialog
- Empty state guides users to create first customer
