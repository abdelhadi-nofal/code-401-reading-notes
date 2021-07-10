# Django
- Django is a Python-based web framework
- Commonly used by developers
- Instagram uses Django


# How Django Really Works?
- Open Source 
- Developed by *Adrian Holovaty*, *Simon Willison*, and *Jacob Kaplan-Moss*, at *the Lawrence Journal-World newspaper*
- Django is continually funded to be maintained, active and progressed.
- > Django’s organization is managed by a non-profit, the DSF, with a miniscule budget. 


# Inroductions - Topics


## Object-relational mapper
> Deﬁne your data models entirely in Python. You get a rich, dynamic database-access API for free — but you can still write SQL if needed.

## URLs and views
> To design URLs for an application, you create a Python module called a URLconf. Like a table of contents for your app, it contains a simple mapping between URL patterns and your views.

>   from django.urls import path

    from . import views

    urlpatterns = [
        path('bands/', views.band_listing, name='band-list'),
        path('bands/<int:band_id>/', views.band_detail, name='band-detail'),
        path('bands/search/', views.band_search, name='band-search'),
    ]

## Templates
- python has a library that renders forms as html
> from django import forms

    class BandContactForm(forms.Form):
        subject = forms.CharField(max_length=100)
        message = forms.CharField()
        sender = forms.EmailField()
        cc_myself = forms.BooleanField(required=False)

## Forms
> Django comes with a full-featured and secure authentication system. It handles user accounts, groups, permissions and cookie-based user sessions. This lets you easily build sites that allow users to create accounts and safely log in/out.

## Admin
> from django.contrib import admin
    from bands.models import Band, Member

    class MemberAdmin(admin.ModelAdmin):
        """Customize the look of the auto-generated admin for the Member model"""
        list_display = ('name', 'instrument')
        list_filter = ('band',)

    admin.site.register(Band)  # Use the default options
    admin.site.register(Member, MemberAdmin)  # Use the customized options

## Internationalization
> Django offers full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones

## Security
> Django provides multiple protections against:

    Clickjacking
    Cross-site scripting
    Cross Site Request Forgery (CSRF)
    SQL injection
    Remote code execution
