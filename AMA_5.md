### Adhikya
**Q: What is the use of `__str__()` method in Python?**

**A:** The `__str__()` method defines how an object is displayed as a string. In Django models, it is commonly used to show a readable name in the admin panel.

```python
class Student(models.Model):
    name = models.CharField(max_length=100)

    def __str__(self):
        return self.name
```

---

### Manikanta 
**Q: Is Django a programming language?**

**A:** No. Django is not a programming language. It is a web framework written in Python that helps build web applications quickly.

---

### Arpit 
**Q: Difference between Templates and Views in Django?**

**A:**

- **Views:** Contain business logic and process requests.
- **Templates:** Handle the presentation layer (HTML).

```python
# views.py
def home(request):
    return render(request, "home.html")
```

---

### Sowmya 
**Q: Can we add a custom 404 page if `DEBUG=True`?**

**A:** No. Django shows its default debug page when `DEBUG=True`. Custom 404 pages work only when `DEBUG=False`.

---

### Arun 
**Q: What is `views.py`?**

**A:** `views.py` contains view functions or classes that receive requests, process data, and return responses.

---

### Harivardhan 
**Q: How do we create a superuser in Django?**

**A:**

```bash
python manage.py createsuperuser
```

Then enter username, email, and password.

---

### Musharaf
**Q: What is REST?**

**A:** REST (Representational State Transfer) is an architectural style used to build APIs using HTTP methods like GET, POST, PUT, PATCH, and DELETE.

---

### Harsha 
**Q: Difference between project `urls.py` and app `urls.py`?**

**A:**

- **Project `urls.py`**: Main URL configuration for the entire project.
- **App `urls.py`**: Handles URLs specific to a single app.

```python
# project urls.py
path('blog/', include('blog.urls'))
```

---

### Sulochana
**Q: Explain CRUD operations in Django.**

**A:**

- **Create** → Add data
- **Read** → Fetch data
- **Update** → Modify data
- **Delete** → Remove data

Example:

```python
Student.objects.create(name="Naman")
Student.objects.all()
student.save()
student.delete()
```

---

### Vasu
**Q: Tell me some HTTP status codes.**

**A:**

| Code | Meaning |
|--------|---------|
| 200 | OK |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

### Rovinpal 
**Q: What is the purpose of Django apps?**

**A:** Django apps help organize features into reusable modules. For example, authentication, blog, and payments can be separate apps.

---

### Haritha
**Q: Is Django open-source?**

**A:** Yes. Django is a free and open-source Python web framework maintained by the Django community.

---

### Vikas 
**Q: What does the `render()` method do in Django?**

**A:** `render()` combines a template with data and returns an HTTP response.

```python
from django.shortcuts import render

def home(request):
    return render(request, "home.html")
```
