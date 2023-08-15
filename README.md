# Django-Cheat-Sheet
Django Cheat Sheet Python Developers

# Setup environment for a new Django project
- Create a new Project folder and navigate to it with $ cd <Project>
- Create Python virtual env $ python3 -m venv venv
- Activate virtual env $ source venv/bin/activate
- To deactivate virtual env $ deactivate (In case you need)
- Install django $ pip install django
- Install other package dependencies with $ pip install <package_name>. The best way to install all necessary packages is to create a requirements.txt file and list
  all the packages and run $ pip install -r requirements.txt

# Start a new Django project

  

# Integrate django-summer note editor with Django Project.

```
# Step 1: install the Summernote package
  pip install django-summernote

# Step 2: settings.py

INSTALLED_APPS = (
    'django_summernote',
)
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media/')
X_FRAME_OPTIONS = 'SAMEORIGIN'

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT) 
    
# Step 3: urls.py

urlpatterns = [
    path('summernote/', include('django_summernote.urls')),
]

# Step 2: admin.py
from django_summernote.admin import SummernoteModelAdmin
from .models import Post

class PostAdmin(SummernoteModelAdmin):
    summernote_fields = ('content',)

admin.site.register(Post, PostAdmin)
```

Check the Post model content field in Django admin. 
