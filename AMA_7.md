# Django AMA / Interview Questions & Answers

## Adhikya Edammala

### Q: What are Generic Views?

**Answer:**
Generic Views are pre-built class-based views provided by Django to perform common operations like listing, creating, updating, and deleting objects with minimal code.

Common Generic Views:
- ListView
- DetailView
- CreateView
- UpdateView
- DeleteView
- TemplateView

Example:

```python
from django.views.generic import ListView
from .models import Post

class PostListView(ListView):
    model = Post
    template_name = "posts/list.html"
```

**Advantage:**
- Less boilerplate code
- Reusable
- Easier to maintain

---

## Allanki VV Manikanta Sai

### Q: What is a DB Server in Render?

**Answer:**
A DB Server in Render is a managed PostgreSQL database service that stores your application's data.

Your Django application connects to it using the `DATABASE_URL`.

Example:

```text
postgresql://username:password@host:5432/database_name
```

The database server is separate from your Django application and can be accessed over the internet using secure credentials.

---

## Arpit Yadav

### Q: What is the use of `forms.ModelForm`?

**Answer:**
`ModelForm` automatically creates a form from a Django model.

Instead of manually defining each field, Django generates them based on the model.

Example:

```python
class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = "__all__"
```

**Advantages**
- Less code
- Automatic validation
- Easy to save data

```python
form.save()
```

---

## Boorle Sowmya Sri Lakshmi

### Q: Why do we use Redis and Celery?

**Answer:**

**Celery**
- Executes long-running tasks in the background.

Examples:
- Sending emails
- Generating reports
- Image processing
- Notifications

**Redis**
- Acts as the message broker between Django and Celery.
- Stores task queues.

Flow:

```
User Request
      ↓
 Django
      ↓
Redis (Queue)
      ↓
 Celery Worker
      ↓
 Executes Task
```

Without Celery, users would have to wait for long-running tasks to finish before getting a response.

---

## M Harivardhan Reddy

### Q: What is Pagination?

**Answer:**
Pagination divides a large dataset into smaller pages.

Instead of loading all records, Django returns a limited number per page.

Example:

```python
from django.core.paginator import Paginator

paginator = Paginator(posts, 10)
page = request.GET.get("page")
posts = paginator.get_page(page)
```

Benefits:
- Faster loading
- Better performance
- Improved user experience

---

## Md Musharaf

### Q: Why do we use App Namespacing in Django?

**Answer:**
App namespacing prevents URL name conflicts when multiple apps use the same URL names.

Example:

```python
app_name = "posts"
```

urls.py

```python
path("create/", views.create_post, name="create")
```

Template:

```html
<a href="{% url 'posts:create' %}">
```

Without namespacing, Django may not know which `create` URL to use.

---

## Nayunipatruni Harsha Vardhan

### Q: What is `request.FILES`?

**Answer:**
`request.FILES` contains uploaded files submitted through a form.

Example:

```python
if request.method == "POST":
    image = request.FILES["image"]
```

HTML:

```html
<form method="POST" enctype="multipart/form-data">
```

Without:

```html
enctype="multipart/form-data"
```

uploaded files won't be available in `request.FILES`.

---

## Parlapalli Sulochana

### Q: Which field is used to upload videos in Django models?

**Answer:**

Use:

```python
models.FileField()
```

Example:

```python
video = models.FileField(upload_to="videos/")
```

`ImageField` is only for images.

For videos:
- `FileField`
- MP4, AVI, MOV, etc.

---

## Rongala Vasu

### Q: What are MEDIA_URL and MEDIA_ROOT?

**Answer:**

**MEDIA_ROOT**
- Physical directory where uploaded files are stored.

Example:

```python
MEDIA_ROOT = BASE_DIR / "media"
```

**MEDIA_URL**
- URL used to access uploaded files.

Example:

```python
MEDIA_URL = "/media/"
```

Example:

```
media/
    profile.jpg
```

Accessible as:

```
http://127.0.0.1:8000/media/profile.jpg
```

---

## Rovinpal Udupi

### Q: If we change methods in a model, do we have to migrate?

**Answer:**
**No**, if you only change Python methods such as:

```python
def __str__(self):
```

or

```python
def get_absolute_url(self):
```

No migration is needed because the database schema hasn't changed.

Migration is required only when database fields change.

Examples requiring migration:

```python
title = models.CharField(max_length=100)
```

Changing:

- Add field
- Remove field
- Rename field
- Change field type
- Change constraints

Commands:

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## Vikas Mehta

### Q: What is Event Delegation?

**Answer:**
Event Delegation is a JavaScript technique where a parent element handles events for its child elements using event bubbling.

Instead of attaching event listeners to every child, one listener is attached to the parent.

Example:

```javascript
document.getElementById("posts").addEventListener("click", function(event) {
    if (event.target.classList.contains("delete-btn")) {
        console.log("Delete clicked");
    }
});
```

Benefits:
- Better performance
- Less memory usage
- Works for dynamically added elements
- Cleaner code
