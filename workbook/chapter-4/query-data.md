## Exercise 4.2 - Querying Data for Index Page

#### 1. Edit project/views.py

```python
from django.shortcuts import render
from apps.recipes.models import Recipe, Category

def home(request):
   recipes = Recipe.objects.all()[:3]
   print recipes

   return render(request, 'home.html', {
      'recipes': recipes,
   })
```

#### 2. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Queried data for index page"
(venv)website.com $ git status
```

#### Challenge: Feeling Advanced? You look advanced. You can do this!
> Why don’t you try querying 3 recipes and sort them randomly? Hint: you are going to use a questions mark (?) somewhere in your query.
