
```sh
#Create virtual environment
python3.10 -m venv .venv

#  Activate virtual environment
source .venv/bin/activate

pip freeze > requirements.txt

# Install dependencies
pip install -r requirements.txt

# Create database
python manage.py makemigrations

# Run migrations
python manage.py migrate

# Run server
python manage.py runserver