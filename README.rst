Django cookie policy
=====================

django-cookie-policy is a reusable application for managing visitors consent with respect to the cookies law in Django project.
It allows a server side control of all the feature of the website that are cookie-related.

Features:
-------------

* a variable called ``cookie_accepted`` is added automatically to all the templates

* cookie acceptance banner and cookie policy page are already availbale for customization

* cookies are stored in the visitor browser


Configuration
-------------

1. Add ``cookie_policy`` to your ``INSTALLED_APPS``.

2. Add ``django.core.context_processors.request``
   to ``TEMPLATE_CONTEXT_PROCESSORS`` if it is not already added.

3. Include django-cookie-policy urls in ``urls.py``::

    url(r'^cookies/', include('cookie_policy.urls'))

Usage
-----------

In order to display the cookie policy banner, just add the following lines to your templates:

``{% if not cookie_accepted %}
{% include 'cookie_policy/banner.html' %}
{% endif %}``