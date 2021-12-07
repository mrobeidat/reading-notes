#  Django’s user models
**Django’s user models** have to do with authentication and storing data about users. When you start a default Django project, your project is configured to use the default user model.

The default user model makes it possible for users to log in to your site using a username and password. You get user-related functionality such as limiting access to some parts of the site to authenticated users and the admin functionality for free.

## How to Create a Custom Django User Model
1. Create a new app
2. Create the Custom User Model in `models.py`
3. Create the User model manager
4. Update settings module (aka `settings.py`)
     1. Run Migrations
     2. Update `settings.py`
     3. Run Migrations again
     4. Create a superuser
     5. Some practical thoughts
5. Create the Forms for Register, Change, and Admin-Level Create
6. Update the Django Admin
7. Challenge. With the above, try to add a new field to your model.

## Djangox
A framework for launching new Django projects quickly. Comes with a complete user authentication flow, custom user model, and social authentication options via Gmail, Facebook, Twitter, etc.

```bash 
$ git clone https://github.com/wsvincent/djangox.git
$ cd djangox
$ pipenv install
$ pipenv shell
