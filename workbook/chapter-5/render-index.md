## Exercise 5.1 - Rendering the Index Page

#### 1. Place all HTML files into `/templates/` folder and all static files into `/static/` folder.

#### 2. Edit `/project/urls.py`

```python
from django.conf import settings # add this
from django.conf.urls.static import static # add this
from django.conf.urls import include, url
from django.contrib import admin
from . import views

urlpatterns = [
    url(r'^admin/', include(admin.site.urls)),
    url(r'^$', views.home),
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT) # add this
```

#### 3. Edit `/templates/home.html`

```html
<!-- RECIPES -->
<div class="carousel">
    <ul>
        {% for recipe in recipes %}
            <li>
                <img src="{{ recipe.photo.url }}" alt="">
                <div class="slide-info">
                    <h3>{{ recipe.title }}</h3>
                    <p>{{ recipe.description }}</p>
                    <p class="meta">
                        <span class="time">Ready in {{ recipe.cooktime }} mins</span>
                        <span class="difficulty">{{ recipe.calories }} kcals</span>
                        <a href="/{{ recipe.category.slug }}/{{ recipe.id }}/{{ recipe.slug }}/" 
                        	class="button small">Try this one</a>
                    </p>
                </div>
            </li>
        {% endfor %}
    </ul>
</div>
<!-- RECIPES -->
```

#### 4. Run the site server and browse the index page.

```bash
(venv)website.com $ python manage.py runserver
```

#### 5. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Rendered the index page"
(venv)website.com $ git status
```

#### Challenge: Feeling Advanced? You look advanced. You can do this!
> If you haven’t noticed, these article links are really tedious to construct and quite messy! Why don’t you try applying **DRY** to the URLs? Hint: there is a method in Models called `get_absolute_url`. Do the simplest implementation and your templates will be much cleaner.

