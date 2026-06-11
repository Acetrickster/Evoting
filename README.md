# Online Voting System 2026

A Django-based online voting application with user registration, login, and SMS OTP verification.

## Features

- Voter registration with Aadhaar and mobile number
- SMS OTP verification for registration and login
- Admin dashboard for managing candidates and elections
- Responsive HTML/CSS front-end
- Built with Django 5.2.6

## Project Structure

- `manage.py` — Django management entrypoint
- `OVS_SRGI/` — Django app and project files
- `OVS_SRGI/settings.py` — project settings
- `OVS_SRGI/urls.py` — routes
- `OVS_SRGI/views.py` — app views
- `OVS_SRGI/sms_utils.py` — Twilio SMS helpers
- `requirements.txt` — Python dependencies
- `pyproject.toml` — package metadata
- `Procfile` — render/heroku start command
- `runtime.txt` — Python version

## Requirements
- Python 3.12+
- Django 5.2.6
- Pillow
- qrcode
- Twilio account for SMS
- SQLite (default) or another database if configured

## Setup

1. Clone the repository
   ```bash
   git clone https://github.com/Acetrickster/Evoting.git
   cd Evoting
2. Create virtual environment
   `python -m venv venv`
   `source venv/bin/activate`
3. install dependencies
   `pip install -r requirements.txt`

--------------------------------------------------------------------------------------------
Configuration
Create a .env file or set environment variables:
 `DEBUG=False
 SECRET_KEY=your-secret-key-here
 ALLOWED_HOSTS=localhost,127.0.0.1
 TWILIO_ACCOUNT_SID=your-twilio-account-sid
 TWILIO_AUTH_TOKEN=your-twilio-auth-token
 TWILIO_PHONE_NUMBER=your-twilio-phone-number`

Generate a Django secret key:
`python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"`

Apply migrations:
`python manage.py migrate`

Create a superuser:
`python manage.py createsuperuser`

Start the development server:
`python manage.py runserver`

Then open:

`http://127.0.0.1:8000/
 http://127.0.0.1:8000/registration/
 http://127.0.0.1:8000/login/
 http://127.0.0.1:8000/admin/`
 SMS OTP Setup
 The app uses Twilio to send OTP codes.

Required environment variables:

 `TWILIO_ACCOUNT_SID
 TWILIO_AUTH_TOKEN
 TWILIO_PHONE_NUMBER
 Test SMS
 Register a new user at /registration/
 Provide a valid mobile number
 Request OTP
 Confirm the SMS arrives`

Deployment
This project includes deployment support for platforms like Render or Heroku.

Render / Heroku
Procfile is already included
runtime.txt defines the Python version
requirements.txt contains all dependencies

Start command:
`gunicorn OVS_SRGI.wsgi:application`

Notes
SQLite is used by default. For production, use PostgreSQL or another managed database.
Keep .env and sensitive credentials out of Git.
Ensure DEBUG=False in production.
If SMS fails, verify Twilio credentials and phone number format.
Useful Commands
`python manage.py migrate
python manage.py createsuperuser
python manage.py runserver`

License
MIT License

Copyright (c) 2026 Acetrickster

Permission is hereby granted, free of charge, to any person obtaining a copy
...
