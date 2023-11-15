

## Question 1

Question 1
We’ve scaffolded two models for the assessment app: Thing, and Comment. A Thing can represent anything! It just a name. A Comment can be added to a Thing. Like the Comment model in Blango, they will be mapped together using a generic relationship.
You will need to edit assessment/models.py and make the following changes:
Add the fields necessary to create a generic relationship to the Comment model
Add a comments attribute to Thing with a GenericRelation, which will enable fetching of comments for a Thing
Make sure to import all the necessary classes
Important: After making your changes, you’ll need to run makemigrations and migrate before running the unit tests. You can do this by running the following commands:
```bash
python manage.py makemigrations
python manage.py migrate
```


```python
from django.db import models
from django.conf import settings

# Question 1: Add your imports for generic relationships below
from django.contrib.contenttypes.fields import GenericForeignKey, GenericRelation
from django.contrib.contenttypes.models import ContentType

class Comment(models.Model):
    content = models.TextField()
    # Question 1: Add your fields for generic relationships below
    content_type = models.ForeignKey(ContentType, on_delete=models.CASCADE)
    object_id = models.PositiveIntegerField()
    content_object = GenericForeignKey('content_type', 'object_id')

class Thing(models.Model):
    name = models.TextField()
    owner = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.PROTECT)
    # Question 1: Add your fields for generic relationships below
    comments = GenericRelation(Comment)
```


## Question 2 - Create a Blog
This will be a test of your knowledge of the Bootstrap column system. The URL /question2/ has been configured to call the view question2, which renders the template question2.html. This template has been configured with a container div.
Inside of this div you’ll need to add two rows.
The first row should have two columns. Each of these two columns should take a 50% of the container width at medium breakpoints or above. Below this breakpoint, they should take up 100% width.
The second row should have three columns. At medium breakpoint and above, the columns should take up 25%, 25% and 50%. Below the medium breakpoint, the columns should take up 50%, 50% and 100%.
You can also add the Bootstrap background color classes to help visualize the columns, using them will not affect the assessment. They are:
bg-primary, bg-secondary, bg-success, bg-danger, bg-warning, bg-info, bg-light and bg-dark

And at small sizes. Resize the screen to see the rows and columns change.

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
          integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    <title>Module 1 Question 2</title>
    <style>
        #question-2-container > .row {
            margin-bottom: 20px;
        }
        #question-2-container > .row > div {
            height: 100px;
        }
    </style>
</head>
<body>
<div class="container" id="question-2-container">
    {% comment %}
        Question 2:
        Add your rows and columns inside this div. They are already sized at 100px height.
        Use these classes to color your columns to help see them.
        bg-primary, bg-secondary, bg-success, bg-danger, bg-warning, bg-info, bg-light and bg-dark
        Setting color classes doesn't affect the scoring of your answer.
    {% endcomment %}
</div>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
        crossorigin="anonymous"></script>
</body>
</html>
```

### Question 2 vSolution

```html
<div class="container" id="question-2-container">
    <div class="row">
        <div class="col-md-6 bg-primary"></div>
        <div class="col-md-6 bg-secondary"></div>
    </div>
    <div class="row">
        <div class="col-md-4 bg-success"></div>
        <div class="col-md-4 bg-danger"></div>
        <div class="col-md-4 bg-warning"></div>
    </div>
</div>


