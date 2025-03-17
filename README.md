# StudyBud

A Django-based study platform for connecting learners.

## Deployment on Render

This application is configured for deployment on Render.com.

### Steps to deploy:

1. Create a new account on [Render](https://render.com/) if you don't have one.

2. Connect your GitHub repository to Render.

3. Create a new Web Service and select your repository.

4. Use the following settings:
   - **Name**: studybud (or your preferred name)
   - **Environment**: Python
   - **Build Command**: `./build.sh`
   - **Start Command**: `gunicorn studybud.wsgi:application`

5. Add the following environment variables:
   - `SECRET_KEY`: (Generate a secure random key)
   - `DEBUG`: false
   - `ALLOWED_HOSTS`: .onrender.com

6. Click "Create Web Service"

### Database Setup:

The application is configured to use:
- SQLite3 for local development
- PostgreSQL on Render (automatically configured via render.yaml)

The render.yaml file will automatically create and link a PostgreSQL database to your web service. No manual database setup is required.

## Local Development

1. Clone the repository
2. Create a virtual environment: `python -m venv venv`
3. Activate the virtual environment:
   - Windows: `venv\Scripts\activate`
   - Mac/Linux: `source venv/bin/activate`
4. Install dependencies: `pip install -r requirements.txt`
5. Create a `.env` file in the root directory with the following variables:
   ```
   SECRET_KEY=your_secret_key
   DEBUG=True
   ALLOWED_HOSTS=localhost,127.0.0.1
   ```
6. Run migrations: `python manage.py migrate`
7. Start the server: `python manage.py runserver`

## Features

- User authentication
- Study rooms
- Discussion forums
- User profiles
