# Backend - Symfony Template App

This is the **backend** of the project, built with **Symfony**.

It provides APIs for the frontend and includes a basic **health check endpoint**.

## 🚀 Project Setup

### Install dependencies

```bash
composer install
```

### Run the local server

```bash
symfony server:start
```

### Health Check

A simple health check endpoint is available at:
GET /health

Example response:
{
"status": "ok",
"timestamp": 1692212213
}
