# Permissions & Postgresql

## DRF Permissions 

### Permissions 

***Authentication or identification by itself is not usually sufficient to gain access to information or code. For that, the entity requesting access must have authorization.*** 

***Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.***

***The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the IsAuthenticated class in REST framework.***

### How permissions are determined 

***Permissions in REST framework are always defined as a list of permission classes.*** 

### Object level permissions

***REST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.***

***Object level permissions are run by REST framework's generic views when .get_object() is called. As with view level permissions, an exceptions.PermissionDenied exception will be raised if the user is not allowed to act on the given object.***

*For example:* 

    def get_object(self):
        obj = get_object_or_404(self.get_queryset(), pk=self.kwargs["pk"])
        self.check_object_permissions(self.request, obj)
        return obj

## API Reference 

### AllowAny 

*The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.* 

*This permission is not strictly required, since you can achieve the same result by using an empty list or tuple for the permissions setting, but you may find it useful to specify this class because it makes the intention explicit.*

### IsAuthenticated 

*The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.*

*This permission is suitable if you want your API to only be accessible to registered users.*

### IsAdminUser 

*The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.*

*This permission is suitable if you want your API to only be accessible to a subset of trusted administrators.*

### IsAuthenticatedOrReadOnly 

*The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.*

*This permission is suitable if you want to your API to allow read permissions to anonymous users, and only allow write permissions to authenticated users.*

### DjangoModelPermissions 

*This permission class ties into Django's standard django.contrib.auth model permissions. This permission must only be applied to views that have a .queryset property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.* 

*To use custom model permissions, override DjangoModelPermissions and set the .perms_map property. Refer to the source code for details.*

### DjangoModelPermissionsOrAnonReadOnly 

*Similar to DjangoModelPermissions, but also allows unauthenticated users to have read-only access to the API.* 

### DjangoObjectPermissions 

*This permission class ties into Django's standard object permissions framework that allows per-object permissions on models. In order to use this permission class, you'll also need to add a permission backend that supports object-level permissions, such as django-guardian.*

*As with DjangoModelPermissions you can use custom model permissions by overriding DjangoObjectPermissions and setting the .perms_map property. Refer to the source code for details.* 

## Custom permissions 

*To implement a custom permission, override BasePermission and implement either, or both, of the following methods:*

* .has_permission(self, request, view)
* .has_object_permission(self, request, view, obj)

## Overview of access restriction methods 

*REST framework offers three different methods to customize access restrictions on a case-by-case basis. These apply in different scenarios and have different effects and limitations.* 

* queryset/get_queryset(): Limits the general visibility of existing objects from the database.

* permission_classes/get_permissions(): General permission checks based on the current action, request and targeted object.

* serializer_class/get_serializer(): Instance level restrictions that apply to all objects on input and output.

## Third party packages 

### DRF - Access Policy 

*The Django REST - Access Policy package provides a way to define complex access rules in declarative policy classes that are attached to view sets or function-based views. The policies are defined in JSON in a format similar to AWS' Identity & Access Management policies.* 

### Composed Permissions 

*The Composed Permissions package provides a simple way to define complex and multi-depth (with logic operators) permission objects, using small and reusable components.* 

### REST Condition 

*The REST Condition package is another extension for building complex permissions in a simple and convenient way. The extension allows you to combine permissions with logical operators.* 

### DRY Rest Permissions 

*The DRY Rest Permissions package provides the ability to define different permissions for individual default and custom actions.*

### Django Rest Framework Roles 

*The Django Rest Framework Roles package makes it easier to parameterize your API over multiple types of users.*

### Django REST Framework API Key 

*The Django REST Framework API Key package provides permissions classes, models and helpers to add API key authorization to your API.*

### Django Rest Framework Role Filters 

*The Django Rest Framework Role Filters package provides simple filtering over multiple types of roles.*

### Django Rest Framework PSQ

*The Django Rest Framework PSQ package is an extension that gives support for having action-based permission_classes, serializer_class, and queryset dependent on permission-based rules.*
