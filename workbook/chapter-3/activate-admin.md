## Exercise 3.2 - Activating Models in the Admin

#### 1. Edit `/apps/recipes/admin.py`

```python
from django.contrib import admin
from .models import Category, Recipe

admin.site.register(Category)
admin.site.register(Recipe)
```

#### 2. Run the site server and browse admin site

```bash
(venv)website.com $ python manage.py runserver
```

#### 3. In your admin site, populate your database with `2 categories` and `5 recipes`. Don’t forget to upload photos!

**Suggested category names:**

| Title 		| Slug			|
|------------	|------------	|
| Breakfast	| breakfast	|
| Mains		| mains		|



#### 4. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Activated models in Admin site"
(venv)website.com $ git status
```

#### Challenge: Feeling Advanced? You look advanced. You can do this!

> The slug is usually the same as the article title but only supports dashes instead of spaces. Why don’t you try implementing an autofill feature for the slug field? **Hint:** use ModelAdmin’s `prepopulated_fields `option.
