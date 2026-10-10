# Document Vault
 
A secure document storage API where users keep files in folders and control exactly who can access them.
 
## Aim
 
This is a learning project. The goal is to understand, by building a real working product, how these backend topics fit together:
 
- **Authentication:** registration, login, password hashing, access and refresh tokens
- **Authorization:** roles, per-resource permissions, permission inheritance
- **Database design:** users, folder trees, files, permissions, share links, audit logs
- **OOP:** clean class design, separation of layers, reusable permission rules
- **FastAPI:** building and structuring a production-style API
No AI integration. The focus is on security and solid backend design.
 
## Description
 
Think of a simplified Google Drive without the editor. Users create folders, upload files, and share them with other people at different access levels.
 
Features:
 
- User registration and login with secure password storage and JWT tokens
- Folders and files with an owner
- Roles per resource: owner, editor, viewer
- Permissions that inherit down the folder tree, with per-item overrides
- Expiring share links
- Audit log of who did what and when
The central question the system answers: *can this user perform this action on this resource?*
 
## Tech Stack
 
- Python 3.11+
- FastAPI
- PostgreSQL
- SQLAlchemy 2.0 and Alembic
- Pydantic
## Project Structure
 
```
vault/
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── core/          # settings, security helpers
│   │   ├── db/            # connection and session
│   │   ├── models/        # database tables
│   │   ├── schemas/       # request/response shapes
│   │   ├── repositories/  # database queries
│   │   ├── services/      # business logic
│   │   ├── policies/      # permission rules
│   │   └── api/           # routes and dependencies
│   ├── migrations/
│   └── tests/
└── frontend/              # built last
```
 
## Status
 
In progress. The backend is built first, step by step. The frontend comes after the backend is complete and tested.