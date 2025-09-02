# Copilot Instructions for `finance-django-backend`

## Overview
This project is a Django-based backend for managing financial operations. It is organized into multiple apps, each responsible for a specific domain of functionality. The architecture follows Django's standard app-based structure, with additional customizations for permissions, tasks, and integrations.

### Key Components
- **Core**: Contains project-wide settings, URL routing, and WSGI/ASGI configurations.
  - Example: `core/settings.py`, `core/urls.py`
- **Authentication**: Manages user authentication and related utilities.
  - Example: `authentication/views.py`, `authentication/utils.py`
- **Client**: Handles client-related operations, including forms and wizards.
  - Example: `client/forms.py`, `client/wizard.py`
- **Finance**: Implements financial models, serializers, and tasks.
  - Example: `finance/models.py`, `finance/serializers.py`, `finance/tasks.py`
- **Group**: Manages group-related data and operations.
  - Example: `group/models.py`, `group/serializers.py`
- **TransactionLog**: Middleware and models for logging transactions.
  - Example: `transactionLog/middleware.py`, `transactionLog/models.py`

### Data Flow
1. **Request Handling**: Requests are routed through `core/urls.py` to the appropriate app.
2. **Business Logic**: Each app encapsulates its domain logic in `views.py`, `models.py`, and `utils.py`.
3. **Database Operations**: Managed via Django ORM with migrations stored in `migrations/` directories.
4. **Asynchronous Tasks**: Defined in `finance/tasks.py` and executed using Celery.

## Developer Workflows

### Setting Up the Environment
1. Create a virtual environment:
   ```powershell
   python -m venv venv
   & .\venv\Scripts\Activate.ps1
   ```
2. Install dependencies:
   ```powershell
   pip install -r requirements.txt
   ```
3. Set up the database:
   ```powershell
   python manage.py migrate
   ```

### Running the Project
Start the development server:
```powershell
python manage.py runserver
```

### Running Tests
Run all tests:
```powershell
python manage.py test
```

### Debugging
- Use `print` statements or logging in `views.py` and `utils.py`.
- For Celery tasks, monitor logs to debug asynchronous operations.

## Project-Specific Conventions
- **Custom Permissions**: Defined in `finance/custompermissions.py`.
- **Celery Integration**: Configured in `core/celery.py`.
- **Templates**: Organized under `templates/<app_name>/`.
- **Static Files**: Ensure proper organization and linking in templates.

## External Dependencies
- **Django**: Core framework for the backend.
- **Celery**: For asynchronous task execution.
- **Database**: Ensure compatibility with the configured database engine in `settings.py`.

## Examples
- Adding a new model:
  1. Define the model in `models.py`.
  2. Create and apply migrations:
     ```powershell
     python manage.py makemigrations
     python manage.py migrate
     ```
- Adding a new Celery task:
  1. Define the task in `tasks.py`.
  2. Ensure the task is registered and monitored in the Celery worker logs.

---

Feel free to update this file as the project evolves. For any unclear sections, provide feedback to improve these instructions.
