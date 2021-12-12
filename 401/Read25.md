# Permissions & Postgresql

## Permissions

![permissions](https://miro.medium.com/max/1400/1*ROdmejG_fHetEfwY7HS45w.png)

Together with authentication and throttling, permissions determine whether a request should be granted or denied access.

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the `request.user` and `request.auth` properties to determine if the incoming request should be permitted.

### How permissions are determined

Permissions in REST framework are always defined as a list of permission classes.

Before running the main body of the view each permission in the list is checked. If any permission check fails, an `exceptions.PermissionDenied` or `exceptions.NotAuthenticated` exception will be raised, and the main body of the view will not run.

### Object level permissions

REST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.

Object level permissions are run by REST framework's generic views when `.get_object()` is called. As with view level permissions, an `exceptions.PermissionDenied` exception will be raised if the user is not allowed to act on the given object.

### Setting the permission policy

The default permission policy may be set globally, using the `DEFAULT_PERMISSION_CLASSES` setting. For example.

    REST_FRAMEWORK = {
        'DEFAULT_PERMISSION_CLASSES': [
            'rest_framework.permissions.IsAuthenticated',
        ]
    }

## API Reference

### AllowAny

The `AllowAny` permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

### IsAuthenticated

The ``IsAuthenticated`` permission class will deny permission to any unauthenticated user, and allow permission otherwise.

### IsAdminUser

The `IsAdminUser` permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

### IsAuthenticatedOrReadOnly

The `IsAuthenticatedOrReadOnly` will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.
### DjangoModelPermissions

This permission class ties into Django's standard django.contrib.auth model permissions. This permission must only be applied to views that have a .queryset property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.

* POST requests require the user to have the add permission on the model.
* PUT and PATCH requests require the user to have the change permission on the model.
* DELETE requests require the user to have the delete permission on the model.

### Custom permissions

To implement a custom permission, override BasePermission and implement either, or both, of the following methods:

* .has_permission(self, request, view)
* .has_object_permission(self, request, view, obj)

The methods should return True if the request should be granted access, and False otherwise.
