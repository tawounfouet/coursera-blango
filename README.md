# Blango
A Blogging application written in django.

## Setup and Installation
```bash
#Create virtual environment
python3.10 -m venv _venv

#  Activate virtual environment
source _venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create database
python manage.py makemigrations

# Run migrations
python manage.py migrate

# Run server
python manage.py runserver 9000

```


### Acknowledgements
- [Advanced Django: Mastering Django and Django Rest Framework Specialization Offered by Codio](https://www.coursera.org/specializations/codio-advanced-django-and-django-rest-framework)
