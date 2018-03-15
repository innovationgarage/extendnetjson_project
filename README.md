# extendnetjson_project
Example project for extending https://github.com/openwisp/django-netjsonconfig

This project completes and corrects the documentation at [Extending
django-netjsonconfig](https://github.com/openwisp/django-netjsonconfig#extending-django-netjsonconfig).
Specifically, the following errors have been corrected:

* In extendnetjson_app/models.py: Override all foreign keys to point
  to the concrete (extended) models. This is pretty messy, but
  necessary since django-netjsonconfig does not use
  https://pypi.python.org/pypi/swapper or a similar solution.
* In extendnetjson_app/controller/views.py: All views should have
  'model = Device', not 'model = Config'.
* extendnetjson_app/admin.py: Import extended models before the
  abstract admin classes so that form fields can be instantiated.

Furthermore, the following additional configurations have been added:

* In extendnetjson_project/settings.py: STATICFILES_DIRS has been set
  to point to django_netjsonconfig.
* In extendnetjson_app/urls.py and
  extendnetjson_app/controller/urls.py: Set app_name properly
