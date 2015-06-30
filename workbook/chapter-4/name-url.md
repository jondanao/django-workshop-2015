## Exercise 4.1 - Naming the URL for Index Page

#### 1. Edit `/project/urls.py`

```python
from django.conf.urls import include, url
from django.contrib import admin
from . import views

urlpatterns = [
    url(r'^admin/', include(admin.site.urls)),
    url(r'^$', views.home),
]
```

#### 2. Create and edit `/project/views.py`

```python
from django.shortcuts import render

def home(request):
	return render(request, 'home.html')
```

#### 3. Create and edit `/templates/home.html`

```html
<h1>Hello Django!</h1>
```

#### 4. Run the site server and browse the index page. You should see “Hello Django!”.

```bash
(venv)website.com $ python manage.py runserver
```

#### 5. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Wrote the URL for index page"
(venv)website.com $ git status
```