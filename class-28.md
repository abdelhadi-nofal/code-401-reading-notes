# Django CRUD and Forms

* Django eases the process of handling and dealing with forms
text boxes, checkboxes, radio buttons, date pickers and so on.

* Using django can allow doing the following:
Declaring, rendeingr, and validating forms using programmatic mechanisms.
Generic form editing views that can do almost all the work to define pages that can do CRUD create, edit, and delete records associated with a single model instance.

# HTML Forms

```form action="/team_name_url/" method="post"> Enter name: /form>```

* action: The resource/URL where data is to be sent for processing when the form is submitted. If this is not set (or set to an empty string), then the form will be submitted back to the current page URL.

* method: The HTTP method used to send the data: post or get.

* The POST method should always be used if the data is going to result in a change to the server's database because this can be made more resistant to cross-site forgery request attacks. The GET method should only be used for forms that don't change user data (e.g. a search form). It is recommended for when you want to be able to bookmark or share the URL.

# Django form handling process


![image](https://user-images.githubusercontent.com/79086986/125344715-4e013680-e360-11eb-9436-69d36f692822.png)


## Main Things Django Does:

* Display the default form the first time it is requested by the user.
* Receive data from a submit request and bind it to the form.
* Clean and validate the data.
* If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
* If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
* Once all actions are complete, redirect the user to another page.

## Example:

Form
Declaring a Form


```
from django import forms
class RenewBookForm(forms.Form): renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
 ```
 
 Form fields
 
 ``` 
 BooleanField, CharField, ChoiceField, TypedChoiceField, DateField, DateTimeField, DecimalField, DurationField, EmailField, FileField, FilePathField, FloatField, ImageField, IntegerField, GenericIPAddressField, MultipleChoiceField, TypedMultipleChoiceField, NullBooleanField, RegexField, SlugField, TimeField, URLField, UUIDField, ComboField, MultiValueField, SplitDateTimeField, ModelMultipleChoiceField, ModelChoiceField.
 ```
 
 Validation

```
from django.core.exceptions import ValidationError

class RenewBookForm(forms.Form): renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
```

```
def clean_renewal_date(self):
    data = self.cleaned_data['renewal_date']

    # Check if a date is not in the past.
    if data < datetime.date.today():
        raise ValidationError(_('Invalid date - renewal in past'))

    # Check if a date is in the allowed range (+4 weeks from today).
    if data > datetime.date.today() + datetime.timedelta(weeks=4):
        raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))
```

URL configuration

```
urlpatterns += [ path('book/uuid:pk/renew/', views.renew_book_librarian, name='renew-book-librarian'),]



```

### View


##### The template
##### ModelForms

```
from django.forms import ModelForm

from catalog.models import BookInstance

class RenewBookModelForm(ModelForm): class Meta: model = BookInstance fields = ['due_back']

```

