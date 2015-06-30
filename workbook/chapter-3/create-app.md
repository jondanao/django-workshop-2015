## Exercise 3.1 - Creating the Recipes App and its Models

#### 1. Start an app inside the `/apps/` folder

```bash
# On OSX or Linux
(venv)website.com $ cd apps
(venv)website.com/apps $ django-admin.py startapp recipes
```

```bash
# On Windows
(venv)website.com $ cd apps
(venv)website.com/apps $ python -m django-admin startapp articles
```

#### 2. Edit `/apps/recipes/models.py`

```python
from django.db import models

class Category(models.Model):
    title = models.CharField(max_length=200)
    slug = models.SlugField(unique=True)

    class Meta:
        verbose_name_plural = 'Categories'

    def __unicode__(self):
        return self.title

class Recipe(models.Model):
    title = models.CharField(max_length=200)
    slug = models.SlugField(unique=True)
    category = models.ForeignKey(Category)
    description = models.TextField()
    photo = models.FileField()
    ingredients = models.TextField()
    method = models.TextField()

    cooktime = models.IntegerField()
    fat = models.FloatField()
    carbs = models.FloatField()
    protein = models.FloatField()
    calories = models.FloatField()

    def __unicode__(self):
        return self.title
```

#### 3. Edit `/project/settings.py`

```python
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    'apps.recipes',
)
```

#### 4. Create `/apps/__init__.py` and run the migrations

```bash
(venv)website.com $ python manage.py makemigrations
(venv)website.com $ python manage.py migrate
```

#### 5. Inspect the database and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Created the recipes app and its models"
(venv)website.com $ git status
```
