# Django Models

### Models


* Django web applications access and manage data through Python objects 
referred to as models.


 *Models define the structure of stored data, including the field types 
 and possibly also their maximum size, default values, selection list 
 options, help text for documentation, label text for forms, etc.

* The definition of the model is independent of the underlying database — 
you can choose one of several as part of your project settings.


* Models are usually defined in an application's models.py file. They are 
implemented as subclasses of django.db.models.Model, and can include 
fields, methods and metadata. The code fragment below shows a "typical" 
model, named MyModelName:



`from django.db import models

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
`

#### Field Types

1- CharField

2- TextField

3- IntegerField

4-DateField and DateTimeField are used for storing/representing dates and 
date/time information (as Python datetime.date in and datetime.datetime 
objects, respectively)


5- EmailField

6- FileField and ImageField

7- AutoField

7- ForeignKey

8- ManyToManyField

9- Metadata

One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type.

## Django Admin


The Django admin application : can use your models to automatically build a site area that you can use to create, view, update, and delete records. This can save you a lot of time during development, making it very easy to test your models and get a feel for whether you have the right data.
The admin application can also be useful for managing data in production, depending on the type of website. The Django project recommends it only for internal data management (i.e. just for use by admins, or people internal to your organization), as the model-centric approach is not necessarily the best possible interface for all users, and exposes a lot of unnecessary detail about the models.
All the configuration required to include the admin application in your website was done automatically when you created the skeleton project
First, open admin.py (Links to an external site.) in the catalog application, then do from django.contrib import admin
Register the models by copying the following text into the bottom of the file. This code simply imports the models and then calls admin.site.register to register each of them.
In order to view and create records we also need this user to have permissions to manage all our objects. You can create a "superuser" account that has full access to the site and all needed permissions using manage.py (Links to an external site.).
Call the following command : python3 manage.py (Links to an external site.) createsuperuser, in the same directory as manage.py (Links to an external site.), to create the superuser. You will be prompted to enter a username, email address, and strong password.
To login to the site, open the /admin URL (e.g. http://127.0.0.1:8000/admin (Links to an external site.)) and enter your new superuser userid and password credentials (you’ll be redirected to the login page, and then back to the /admin URL after you’ve entered your details).
Django does a pretty good job of creating a basic admin site using the information from the registered models:
Each model has a list of individual records, identified by the string created with the model’s str() - method, and linked to detail views/forms for editing. By default, this view has an action menu at the top that you can use to perform bulk delete operations on records.
The model detail record forms for editing and adding records contain all the fields in the model, laid out vertically in their declaration order.
