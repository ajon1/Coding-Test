# 📝 Take-Home Exercise Instructions

## Project Setup

You have access to a starter repo with:

- `/frontend` → Vue 2 app with basic template
- `/backend` → Symfony PHP app with basic API template

Your task is to implement a small event management system using the provided JSON dataset of 100 events (`dummy_events.json`).

---

## Part 1: Backend (Symfony PHP)

### 1. Endpoints

#### GET `/api/events`

- Returns all events without children.
- Each event should include:
  - `id`, `title`, `status`, `date`, `startTime`, `endTime`, `minutes`
  - `user` (id + name)
  - `businessUnit` (id + name)
  - `billingCodes`

#### GET `/api/events/{id}`

- Returns a single event by id, including all its nested children recursively.

#### PATCH `/api/events/{id}` (Bonus)

- Update one or more properties of an event (`title`, `status`, `startTime`, `endTime`, etc.).

#### DELETE `/api/events/{id}` (Bonus)

- Remove an event by id.

> **Tip**: On backend startup, load the JSON file into a PHP array.  
> `PATCH` / `DELETE` modifies this array in memory.  
> Changes only last until the server restarts.

---

### 2. Implementation Notes

- Use the provided JSON file as the source of truth.
- Ensure children are excluded in the `/api/events` list.
- Include children recursively in `/api/events/{id}`.

---

## Part 2: Frontend (Vue 2 + Bootstrap + Element-UI)

### 1. Display Events Table

- Fetch `/api/events` and display them in a table with:
  - Columns: Title, Status, User, Business Unit, Date, Start Time, End Time, Billing Codes
  - Use Bootstrap/Element-UI for styling.
- Implement pagination (25 items per page).
- Implement filters:
  - Status (multi-select)
  - User (dropdown)
  - Business Unit (dropdown)
  - Date Range

### 2. Recursive Task

- When a row is clicked, fetch `/api/events/{id}` and:
  - Display its children recursively, flattened under the parent with indentation.
  - Optionally highlight different levels or statuses for better visualization.

---

## Part 3: Bonus Tasks

1. **Quality Assurance in the frontend using Jest**

   - Write tests to ensure the table displays correctly, filters work, and children are shown recursively.
   - Focus on verifying behavior, not just individual pieces.

2. **PATCH and DELETE endpoints**

   - Add functionality in the frontend to update event fields (`PATCH`) and remove events (`DELETE`).

3. **Dockerization**
   - Create Docker configurations for both frontend and backend so the app can run with `docker-compose up`.

---

## Requirements

- Keep code clean, readable, and maintainable.
- Use Element-UI + Bootstrap for the frontend.
- Use Symfony best practices for the backend (controllers, services, routing).
- No authentication needed; focus is on data fetching, recursion, pagination, filtering, and basic CRUD operations.

---

## Deliverables

1. Create a GitHub repository for the project.
2. Include updated `/backend` with all required API endpoints.
3. Include updated `/frontend` that consumes the endpoints and displays the table with pagination, filters, and recursive children display.
4. Include bonus tasks if completed:
   - Tests in the frontend verifying table and recursive behavior.
   - Ability to PATCH and DELETE events.
   - Docker configuration for backend and frontend.
5. Share the GitHub repo link.
