### Adhikya Edammala: What are some field options in models?
- `null=True` → Allows NULL in database.
- `blank=True` → Allows empty value in forms.
- `default` → Sets a default value.
- `unique=True` → Ensures values are unique.

### Allanki VV Manikanta Sai: What is CSRF?
- CSRF (Cross-Site Request Forgery) is a security attack where unwanted actions are performed on behalf of a logged-in user.
- Django protects against it using a CSRF token (`{% csrf_token %}`).

### Arpit Yadav: What are Mixins in Django?
- Mixins are reusable classes that add extra functionality to views.
- Example: `LoginRequiredMixin` restricts access to logged-in users.

### Boorle Sowmya Sri Lakshmi: What is the use of decorators in Django?
- Decorators modify the behavior of functions or views.
- Example: `@login_required` ensures only logged-in users can access a view.

### M Harivardhan Reddy: Methods of Template Inheritance
- `{% extends %}` → Inherit a parent template.
- `{% block %}` → Define replaceable sections.
- `{% include %}` → Reuse another template inside a template.

### Md Musharaf: To store images which field do we use?
- `ImageField` is used to upload and store images.

### Nayunipatruni Harsha Vardhan: What is QuerySet?
- A QuerySet is a collection of database queries in Django.
- Example: `User.objects.all()` returns all users.

### Parlapalli Sulochana: What are Django Signals?
- Signals allow actions to be triggered automatically when certain events occur.
- Example: Create a profile automatically when a user is created.

### Rongala Vasu: Do we need to create the User table manually?
- No.
- Django provides a built-in User model and creates its table through migrations.

### Rovinpal Udupi: Model field to upload and store files in Django?
- `FileField` is used to upload and store files.
- `ImageField` is used specifically for images.

### Vikas Mehta: Difference between Static and Media Files
- **Static Files:** CSS, JavaScript, logos, icons (developer-provided).
- **Media Files:** User-uploaded files such as images, videos, and documents.
