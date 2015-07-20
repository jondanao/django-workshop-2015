## Exercise 5.2 - Rendering the Category and Recipe Pages


#### 1. Edit `/project/urls.py`

```python
from django.conf import settings
from django.conf.urls.static import static
from django.conf.urls import include, url
from django.contrib import admin
from . import views

urlpatterns = [
    url(r'^admin/', include(admin.site.urls)),
    url(r'^$', views.home),
    url(r'^(?P<category_slug>[-\w]+)/$', views.category), # add this
    url(r'^(?P<category_slug>[-\w]+)/(?P<recipe_id>\d+)/([-\w]+)/$', views.recipe), # add this
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

#### 2. Edit `/project/views.py` and add these at the bottom

```python
def category(request, category_slug):
    recipes = Recipe.objects.filter(category__slug=category_slug)

    return render(request, 'recipes.html', {
      'recipes': recipes,
    })

def recipe(request, category_slug, recipe_id): 
    recipe = Recipe.objects.get(id=recipe_id)

    return render(request, 'recipe.html', { 
      'recipe': recipe,
    })
```

#### 3. Edit `/templates/recipes.html`

```html
<!-- RECIPES -->
{% for recipe in recipes %}
    <div class="recipe-item">
        <article>
            <a class="recipe-image" 
            	href="/{{ recipe.category.slug }}/{{ recipe.id }}/{{ recipe.slug }}/">
                <img src="{{ recipe.photo.url }}" alt="{{ recipe.title }}">
                <h2 class="recipe-title">{{ recipe.title }}</h2>
            </a>
            
            <p>{{ recipe.description|truncatewords:20 }}</p>
            <div class="recipe-info">
                <span class="total-time">{{ recipe.cooktime }} minutes</span>
                <span class="kcals">{{ recipe.calories }} kcals</span>
                <span class="icons icons vegetarian-icon"></span>
            </div>
        </article>
    </div>
{% endfor %}
<!-- RECIPES -->
```

#### 4. Edit `/apps/recipes/models.py`

```python
class Recipe(models.Model):
	
	...

    def __unicode__(self):
        return self.title

    def ingredients_list(self):
        return self.ingredients.split('\n')

    def method_list(self):
        return self.method.split('\n')
```


#### 5. Edit `/templates/article.html`

```html
<!-- RECIPE -->
<article class="recipes">
    <header class="recipe-header">
        <h1 class="title">{{ recipe.title }}</h1>
        <p>{{ recipe.description }}</p>
        <a class="buttons close" href="#">Close</a>
    </header>
    <div class="recipe-content">
        <div class="details">
            <div class="actions">
                <a class="buttons" href="#">Add to favourites</a>
                <a class="buttons" href="#">Print</a>
            </div>
            <img src="{{ recipe.photo.url }}" alt="Spicy Paneer Skewers">
            <ul class="recipe-info">
                <li><span class="icons cooktime-icon">Cook {{ recipe.cooktime }} mins</span></li>
                <li><span class="icons vegetarian-icon">Vegetarian</span></li>
            </ul>
            <p class="per-serving">Nutrition per serving</p>
            <p>
            		{{ recipe.calories }} kcalories, 
            		protein {{ recipe.protein }}g, 
            		carbohydrate {{ recipe.carbs }}g, 
            		fat {{ recipe.fat }}g
		     </p>
        </div>
        <div class="ingredients">
            <h2 class="title">Ingredient</h2>
            <p><strong>Serves 10</strong></p>
            <ul>
                {{ recipe.ingredients_list|unordered_list }}
            </ul>
        </div>
        <div class="method">
            <h2 class="title">Method</h2>
            <ol>
                {{ recipe.method_list|unordered_list }}
            </ol>
        </div>
    </div>
</article>
<!-- RECIPE -->
```

#### 6. Run the site server and browse all the pages.

```bash
(venv)website.com $ python manage.py runserver
```

#### 7. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Rendered the category and article pages"
(venv)website.com $ git status
```

#### Challenge 1: Feeling Advanced? You look advanced. You can do this!
> Why don’t you try adding highlight to your navigation’s active state when browsing a category or an article? **Hint:** use template inheritance to implement this. Add `class="active"` to the nav’s `<li>` element.

#### Challenge 2: Let's finish the other section pages.
> As you can see, there are sections for `High Protein`, `Low Calorie` and `30 Minute Meals`. These are not really categories based on the Category model. But you can create pseudo categories by querying predefined filters for these sections. **Hint:** Query for recipes with `protein > 35`, `calories < 250` and `cooktime <= 30`.