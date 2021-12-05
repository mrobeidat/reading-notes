## <ins>*Django Models*

Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc.


> Models are usually defined in an application's __`models.py`__ file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.
typical model example would be like : 
 
 ```py
 from django.db import models
class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""
    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...
    # Metadata
    class Meta:
        ordering = ['-my_field_name']
    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])
    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name
 ```
 
### Model management.
  - Creating and modifying records:
  by defining an instance of the model and then call __save()__.
```py
# Create a new record using the model's constructor.
record = MyModelName(my_field_name="Instance #1")
# Save the object into the database.
record.save()
```
 If primary_key is not declared, the new record will be given one automatically, with the field name __id__

  <ins>Accessing new record fields:
  by using __(.)__ as 

```py
  record.field_name = 'new value'
  record.save()
```
 
- Searching for records
using the model's objects attribute (provided by the base class).

    - .objects.all()
    - .objects.filter(title__contains='text')
      - field_name__match_type='text'
        - eg : contains  , icontains ,iexact ,exact ,in ,gt,startswith ..
        [The Full List](https://docs.djangoproject.com/en/3.1/ref/models/querysets/#field-lookups)



## <ins>*Django Admin*

automatic admin interface. It reads metadata from your models to provide a quick, model-centric interface where trusted users can manage content on your site.

uses __`admin.py`__ to display models in the Django admin panel


- Registering models 
in the __`admin.py`__ located in `(/locallibrary/catalog/admin.py)`

```py
from .models import Model_1, Model_2, Model_3, Model_4
admin.site.register(Model_1)
admin.site.register(Model_2)
admin.site.register(Model_3)
admin.site.register(Model_4)
```

- Creating a superuser

```bash
python3 manage.py createsuperuser
```
