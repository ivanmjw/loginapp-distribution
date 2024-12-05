# Login App Deployment

This is a Django-based login application that tracks user login history.

## Prerequisites
- Docker
- Docker Compose

## Deployment Steps

1. Clone this distribution folder
2. Copy `.env.example` to `.env` and update the values:
   ```bash
   cp .env.example .env
   ```
3. Update the following in `.env`:
   - Generate a new Django secret key
   - Set appropriate ALLOWED_HOSTS
   - Set DEBUG=0 for production

4. Start the application:
   ```bash
   docker-compose up -d
   ```

5. Create a superuser (first time only):
   ```bash
   docker-compose exec web python manage.py createsuperuser
   ```

6. Access the application:
   - Web interface: http://localhost:8000
   - Admin interface: http://localhost:8000/admin

## Volumes
- `static_volume`: Persists static files
- `data_volume`: Persists SQLite database

## Security Notes
- Always change the default secret key
- Use strong passwords
- Consider using a production-grade database for larger deployments 