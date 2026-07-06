# Django & Web Development Interview Questions

## 1. What is Middleware?

Middleware is a layer between the request and the response in Django. It processes every request before it reaches the view and every response before it is sent back to the client.

### Uses:
- Authentication
- Session management
- Security
- Logging
- CSRF protection
- Caching

### Request Flow

```
Client
   ↓
Middleware
   ↓
URL Routing
   ↓
View
   ↓
Response
   ↑
Middleware
   ↑
Client
```

Example:
```python
class MyMiddleware:
    def __init__(self, get_response):
        self.get_response = get_response

    def __call__(self, request):
        print("Before View")

        response = self.get_response(request)

        print("After View")
        return response
```

---

# 2. What is a Context Processor?

A context processor is a function that adds variables automatically to the template context, so you don't need to pass them from every view.

### Example

```python
def site_name(request):
    return {
        "site_name": "Reddit Clone"
    }
```

In `settings.py`

```python
TEMPLATES = [
    {
        "OPTIONS": {
            "context_processors": [
                "myapp.context_processors.site_name",
            ]
        }
    }
]
```

Now every template can use

```html
{{ site_name }}
```

without passing it from the view.

---

# 3. What is the use of HTMX in Elasticsearch?

HTMX is **not a part of Elasticsearch**.

HTMX is a frontend library that allows you to update parts of a webpage without writing JavaScript.

It is commonly used **with Django**.

When searching with Elasticsearch:

- User types in the search box.
- HTMX sends AJAX requests automatically.
- Django queries Elasticsearch.
- Only the search results section updates.
- No full page reload occurs.

Benefits:
- Fast searching
- Better user experience
- Less JavaScript
- Live search

Flow:

```
User Types
      ↓
HTMX Request
      ↓
Django View
      ↓
Elasticsearch
      ↓
Results Returned
      ↓
Only Search Section Updates
```

---

# 4. Difference Between Documents and Indexes in Elasticsearch

| Index | Document |
|--------|----------|
| Similar to a database | Similar to a row/record |
| Stores many documents | Stores one piece of data |
| Example: products | Example: one product |
| Contains mappings | Contains actual values |

Example

Index:

```
products
```

Document

```json
{
    "name": "Laptop",
    "price": 65000,
    "brand": "Dell"
}
```

One index can contain millions of documents.

---

# 5. Difference Between CharField and TextField

| CharField | TextField |
|------------|-----------|
| Short text | Long text |
| Requires max_length | No max_length required |
| Stored efficiently for short strings | Suitable for large text |
| Used for names, emails | Used for descriptions, posts |

Example

```python
name = models.CharField(max_length=100)

description = models.TextField()
```

Use:
- Name → CharField
- Email → CharField
- Address → TextField
- Post Content → TextField

---

# 6. Difference Between null=True and blank=True

| null=True | blank=True |
|------------|------------|
| Database level | Form validation level |
| Database stores NULL | Form allows empty value |
| Used mainly for database | Used for forms/admin |

Example

```python
phone = models.CharField(
    max_length=15,
    null=True,
    blank=True
)
```

Meaning:

- `null=True` → Database can store NULL.
- `blank=True` → User can leave the field empty in forms.

---

# 7. What is the use of Meta class?

The `Meta` class provides additional information (metadata) about a Django model.

Common uses:

- Ordering
- Table name
- Verbose name
- Constraints
- Permissions

Example

```python
class Post(models.Model):
    title = models.CharField(max_length=100)

    class Meta:
        ordering = ["-id"]
        db_table = "posts"
```

Here:

- `ordering` sorts records by descending ID.
- `db_table` changes the database table name.

---

# 8. Why do we use AbstractUser?

`AbstractUser` is used to create a custom user model while keeping Django's built-in authentication features.

Reasons:

- Add custom fields
- Modify authentication
- Future flexibility

Example

```python
from django.contrib.auth.models import AbstractUser

class User(AbstractUser):
    bio = models.TextField(blank=True)
    profile_picture = models.ImageField(upload_to="profiles/", blank=True)
```

Advantages:

- Extend default user model
- No need to create authentication from scratch
- Recommended by Django

---

# 9. Difference Between Flexbox and Grid

| Flexbox | Grid |
|----------|------|
| One-dimensional | Two-dimensional |
| Works in row OR column | Works in rows AND columns |
| Best for components | Best for page layouts |
| Easier for alignment | Easier for complex layouts |

### Flexbox Example

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Grid Example

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### When to use

Use **Flexbox** when:
- Navigation bar
- Buttons
- Cards in one row
- Centering elements

Use **Grid** when:
- Dashboard
- Entire webpage layout
- Gallery
- Complex responsive designs
