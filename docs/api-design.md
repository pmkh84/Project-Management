# ProjectHub API Design

Base URL: /api/v1/

## Create Task

POST /tasks/

Authentication: Required
Permission: Team Admin

Request:
- project_id: integer (required)
- title: string (required)
- assignee_id: integer (optional)
- priority: low | medium | high

Response:
- 201: Task created
- 400: Invalid input
- 401: Not authenticated
- 403: Permission denied
- 404: Project not found