
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

python manage.py createsuperuser
- Username: admin
- Email_address: admin@example.com
- Password: admin

```

## Project Setup

```sh
python3 manage.py startapp blog
```


## Content Type

```sh
python3 manage.py shell

from blog.models import Post, Comment
from django.contrib.auth.models import User
p = Post.objects.first()
u = User.objects.first()
c1 = Comment(creator=u, content="What a great post!", content_object=p)
c1.save()
c1.content_object
# Out[7]: <Post: An Example Post>



c2 = Comment(creator=u, content="I like myself! bis ", content_object=u)
c2.save()
c2.content_object
# Out[10]: <User: username
```


```sh

# pip install crispy-bootstrap5
pip install django-crispy-forms

# 
pip3 install django-configurations dj-database-url

# Security password
pip3 install "django[argon2]"

# Database optimisation
pip3 install django-debug-toolbar

pip freeze > requirements.txt