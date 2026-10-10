# ProjectHub — Backend Architecture

**Version:** 0.1  
**Status:** Proposed

## Architecture Style

Modular Monolith using Django and Django REST Framework.

## Main Components

- **Accounts:** User management and authentication
- **Teams:** Team membership and role-based access
- **Projects:** Project management
- **Tasks:** Task management and comments
- **Activity:** Audit and activity logging

## Request Flow

HTTP Request → URL Router → View → Serializer/Permission → Service → Django ORM → PostgreSQL

The View coordinates requests and responses. Serializers validate API data. Permission checks enforce authorization. Services handle non-trivial business operations.

## Core Architectural Decisions

1. Use a Custom User Model before initial migrations.
2. Use PostgreSQL as the primary relational database.
3. Use Django ORM for database operations.
4. Enforce team-level authorization on all protected resources.
5. Keep reusable business logic outside HTTP-specific views.
6. Use database transactions for dependent writes.
7. Write automated tests for core business rules and permissions.
8. Build one deployable backend, not microservices.

## Planned Structure

- backend/config/
- backend/apps/accounts/
- backend/apps/teams/
- backend/apps/projects/
- backend/apps/tasks/
- backend/apps/activity/
- frontend/
- docs/

## Deferred Decisions

- JWT versus session authentication
- Detailed logging and monitoring strategy
- Task notification delivery architecture
- Deployment infrastructure

These decisions will be finalized before their implementation.