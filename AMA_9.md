## 1. What is the use of Celery?
**Answer:**  
Celery is used to execute time-consuming tasks asynchronously in the background, such as sending emails, generating reports, and processing files.

---

## 2. How do you insert and remove an element at a particular position in a Python list?
**Insert:**
```python
lst.insert(index, value)
```

**Remove:**
```python
lst.pop(index)
# or
del lst[index]
```

---

## 3. What is the purpose of Exchange in RabbitMQ?
**Answer:**  
An Exchange receives messages from producers and routes them to one or more queues based on routing rules (Direct, Fanout, Topic, or Headers).

---

## 4. What is the use of a Dockerfile?
**Answer:**  
A Dockerfile contains instructions to build a Docker image, packaging the application, dependencies, and runtime environment.

---

## 5. What is HyperlinkedModelSerializer?
**Answer:**  
`HyperlinkedModelSerializer` is a Django REST Framework serializer that represents related objects using URLs instead of primary keys.

---

## 6. What are the different types of methods in Python?
- **Instance Method:** Uses `self` and accesses object data.
- **Class Method:** Uses `cls` and accesses class data.
- **Static Method:** Uses neither `self` nor `cls`; acts like a regular function inside the class.

---

## 7. What is the use of Django REST Framework (DRF)?
**Answer:**  
DRF is used to build RESTful APIs in Django with features like serializers, authentication, permissions, pagination, and viewsets.

---

## 8. What is Celery Beat?
**Answer:**  
Celery Beat is a scheduler that runs Celery tasks at specified times or intervals (similar to Cron jobs).

---

## 9. Difference between Session Storage and Local Storage

| Session Storage | Local Storage |
|-----------------|---------------|
| Data lasts until the browser/tab is closed. | Data persists until manually deleted. |
| Not shared across tabs. | Shared across tabs of the same origin. |
| Used for temporary data. | Used for persistent user preferences. |
