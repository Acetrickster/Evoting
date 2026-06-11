web: gunicorn OVS_SRGI.wsgi:application
release: python manage.py migrate && python manage.py collectstatic --noinput
