# Authentication & Production Server

> # JSON Web Tokens

## What is JSON Web Token?

***is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object.*** 

## When should you use JSON Web Tokens? 

* Authorization: 

*This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token.* 

* Information Exchange: 

*JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are.* 

## What is the JSON Web Token structure? 

***JSON Web Tokens consist of three parts separated by dots (.), which are:*** 

1. Header
2. Payload
3. Signature

***JWT typically looks like:***

    xxxxx.yyyyy.zzzzz

* Header :

**The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.**

*For example:* 

    {
    "alg": "HS256",
    "typ": "JWT"
    } 

* Payload 

**contains the claims.**

**Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: registered, public, and private claims.** 

- Registered claims:  

*These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims.*

- Public claims: 

*These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace.*

- Private claims: 

*These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.*

## How do JSON Web Tokens work? 

***In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must be taken to prevent security issues. In general, you should not keep tokens longer than required.***

![](https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)

1. The application or client requests authorization to the authorization server. 
2. When the authorization is granted, the authorization server returns an access token to the application.
3. The application uses the access token to access a protected resource (like an API). 

> # DRF JWT Authentication

## How JWT Works? 

***The JWT is just an authorization token that should be included in all requests.***

***The JWT is acquired by exchanging an username + password for an access token and an refresh token.***

***The access token is usually short-lived (expires in 5 min or so, can be customized though).***

***The refresh token lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a full login with username + password again.***

## Installation & Setup 

***we are going to use the djangorestframework_simplejwt library, recommended by the DRF developers.***

    pip install djangorestframework_simplejwt

### settings.py 

    REST_FRAMEWORK = {
        'DEFAULT_AUTHENTICATION_CLASSES': [
            'rest_framework_simplejwt.authentication.JWTAuthentication',
        ],
    }
### urls.py 

    from django.urls import path
    from rest_framework_simplejwt import views as jwt_views

    urlpatterns = [
        # Your URLs...
        path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
        path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
    ]

## What’s The Point of The Refresh Token? 

***in fact it is necessary to make sure the user still have the correct permissions.***

***There is also a security aspect, in a sense that the refresh token only travel in the POST data. And the access token is sent via HTTP header, which may be logged along the way. So this also give a short window, should your access token be compromised.***

> # Django Runserver Is Not Your Production Server 

## A Production Stack 

***A production setup usually consists of multiple components, each designed and built to be really good at one specific thing. They are fast, reliable and very focused.***

## How Does Django Fit In? 

***Django app does not actually run as you would think a server would - waiting for requests and reacting to them. Your project provides a uwsgi.py file, which contains a function to be called by the application server. This function gets a Python object representing the incoming request.***

***This function calls your code, and produces a response object which is passed to the WSGI server. There the response is translated into a HTTP response and is passed back to the web server, which finally delivers it to the user.***
