Building Modern Applications with Django and Vue.js
Learn ow to create a full-stack application with Django, Django REST framework, and Vue.js. Then, learn how to secure your REST API and the Vue.js frontend with Auth0.

## Introduction to Python and Django
Python is a general-purpose programming language and it's among the most popular programming languages in the world nowadays. It's readable, efficient, and easy to learn. Python is also a portable language available for major operating systems such as Linux, Windows, and Mac.

For web developers, Python has many great tools and frameworks that make developers more productive and able to build prototypes in no time. The most popular web framework for development in the Python landscape is Django. Django is advertised as the framework for perfectionists with tight deadlines because of its ability to allow developers to quickly build prototypes.

Django uses the power of Python that offers Django developers a great set of features such as class-based views and a powerful ORM that you can use to model your database requirements without writing any single line of SQL. The Django ORM abstracts away all the complexities of working with databases and, most importantly, doesn't intimidate you when your client has not decided yet on the database system to use. You can start developing using an SQLite database (which doesn't need any special installation) then you can switch to the right database system later on when your client has settled on the right RDBMS (Relational Database Management System) to use.

Django also comes with a powerful migration system that allows you to migrate your database safely and without losing your data when you make changes to the database structure later on.

Another advantage of using the Django web framework is that it has a big and an evolving community. This community has created open source packages for common web development problems, so you don't need to reinvent the wheel when building your project.

Django has an excellent and complete documentation of all the features of the framework supplemented by a set of tutorials created by the community.

Django is also suitable for beginners and you don't have to be an expert in every feature of the framework to start building your web application.

"Django is also suitable for beginners and you don't have to be an expert in every feature of the framework to start building your web application."


2) Introduction to Vue.js and Vue.js Features
Vue.js is a progressive framework for building user interfaces with JavaScript. You can use Vue.js in the view layer of your application or you can use it to build Single Page Applications (SPAs) by combining it with some other frontend tools.

Vue.js took the best of both Angular.js and React into one library. For example, just like React, Vue.js uses a virtual DOM and a component-based approach. It also uses similar syntax to the Angular.js directives (e.g. v-if and v-for)

Vue.js has many features, such as:

1 virtual DOM;

2 reactive and composable view components;

3 great performance;
4  native rendering on iOS and Android thanks to Weex and NativeScript;

5 Bootstrapping the backend Project

6 Before you can create the backend project, you need to install some requirements on your development machine. For Django, you need to have Python 3, PIP, and venv installed.

Please note that you don't need to install a full-fledged database management system to develop with Django. You can use an SQLite database which allows you to have a file-based database that doesn't require any special installation.

## Installing the Requirements
Let's start with Python 3. Chances are that you already have Python 3 installed on your machine. If not, then the process is simple. You just need to head over to the official downloads page and pick the installer for your operating system.

You can check if you have Python 3 installed by running the following command from your terminal or command prompt:

python3 --version
The venv module (part of the Python 3 standard library) allows you to create lightweight virtual environments for your projects. This allows you to have an isolated environments for each Python project (i.e. dependencies are isolated for each project and from the system-wide packages).

Setting up an isolated environment provides you with more control over the installed Python packages. You can have different versions of the same package without having to worry about any conflicts, which allows you to work with different Python projects with different package versions. Also, since each environment can have its own Python binary, this allows you to create various environments with different Python versions.

Once you create a virtual environment, venv will take care of installing the latest Python binary.

Next, you need to install pip, a package manager for Python that, by default, installs packages from the Python Package Index (PyPI).

You can verify if pip is installed on your development machine by running the following command:

# pip or pip3, depending on the environment
pip --version
You should have pip installed if you have installed Python using the official python.org installer (or via Homebrew in MAC). Also, if you are inside a venv environment, pip is already installed. For Linux, you may need to install it separately. If that's your environment, take a look at this guide and this page.

## Creating a Virtual Environment
Once you have all the backend requirements installed, you will have to create a virtual environment for installing your project's dependencies. Head back to your terminal and run the following commands:

# create a directory to your project
mkdir django-vue

# move the cursor to it
cd django-vue

# initialize a virtual env on it
python3 -m venv ./
Next, you need to activate the virtual environment using source:

source ./bin/activate
## Bootstrapping Django
You can now install Django using pip:

pip install django
The next step is to create the Django project using this command:

django-admin startproject djangovue .
Now, execute the following commands to organize your Django project with catalog:

python manage.py startapp catalog
You also need to add this app to the list of installed apps. Open your settings.py file and add the app:

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'catalog'
]
You can then migrate your database and start the development server:

python manage.py migrate
python manage.py runserver
If you navigate to http://127.0.0.1:8000 in a web browser, you will see the following homepage:

Django localhost starter page

## Bootstrapping the frontend Project
Vue.js has a CLI utility that allows developers to quickly generate SPAs. The CLI offers pre-configured build setups for a modern frontend workflow and takes only a few minutes to scaffold a basic project boilerplate. This boilerplate is shipped with features such as hot-reloading, lint-on-save, and production-ready builds.

Before you can install the Vue.js CLI, you need to have a development environment with Node.js 6.x or newer and NPM version 3 or newer. You can install both of them by heading to the official Node.js website and download the right installer for your operating system. For development machines, it's recommended to use NVM.

Next, head over to your terminal or command prompt and run the following command:

npm install -g vue-cli
You may need to add sudo to the NPM command to install commands globally depending on your NPM configuration.

After installing the Vue.js CLI, you will use it to generate a new Vue.js application based on the Webpack template. Inside the Django project's root, run the following command:

# initialize Vue.js with the Webpack template
vue init webpack frontend
Vue.js will ask a bunch of questions while creating your project. You can answer them as follows:

Project name: frontend
Project description: A Vue.js project
Author: Your Name your.name@somewhere.com
Vue build: Runtime + Compiler: recommended for most users
Install vue-router? Yes
Use ESLint to lint your code? Yes
Pick an ESLint preset: Standard
Set up unit tests: No
Setup e2e tests with Nightwatch? No
Should we run npm install for you after the project has been created? (recommended) Yes, use NPM
Then, to run the initial Vue.js project, you can run the following code:

# change working directory to the frontend
cd frontend

# run the NPM dev script
npm run dev
After that, you should be able to visit the Vue.js application in your browser by navigating to http://127.0.0.1:8080.

Vue.js localhost basic application

On the next sections, you will learn how to secure your backend and your frontend with Vue.js. Then, you will learn how to make your Vue.js app securely consume your Django API.

## Creating an Auth0 API
Before you can use secure your app with Auth0, you first need to create an Auth0 account. If you haven't so yet, sign up for a free account now.

Try out the most powerful authentication platform for free.
Get started →
As part of the sign up process, you'll be asked to create a Auth0 domain. For example, django-vue-js.auth0.com. If you'd like to read more about this, you can checkout our learn the basics documentation, that has some great info on Auth0 domains and how to use them.

After that, head over to the API section of the Auth0 dashboard and click on the CREATE API button.

You'll be presented with a form to fill in your API details: the name, the identifier, and the signing algorithm.

## Auth0 Create API Form

You can use the following properties while filling this form:

Name: Django Vue.js API
Identifier: https://django-vuejs-api
Signing Algorithm: RS256
After that, click on the Create button. You'll be taken to a page where you can further customize your API settings.

That's it! You are now ready to integrate your Django application with Auth0

## Integrating Django with Auth0
In this section, you will see how to secure the Django REST API with Auth0.

In the next part, you will build the API, but before that, you will add JWT authentication to your backend using Auth0.

For this reason, you will need to install the Django REST framework. You will also need to install the djangorestframework-jwt package for handling JWT authentication. You will set up djangorestframework-jwt to use Auth0 for signing the JWT tokens.

To do that, head back to your terminal, make sure the virtual environment we previously created is activated, and then run the following commands in the project root to install all packages using pip:

pip install djangorestframework \
  djangorestframework-jwt \
  cryptography \
  python-jose
You may need to install python3-dev if you get problems while installing the cryptography package.

Next, you'll need to add these packages to the list of installed apps in settings.py

INSTALLED_APPS = [
    #...
    'rest_framework',
    'rest_framework_jwt'
]
You will also need to add the REST_FRAMEWORK application definition to settings.py:

REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': (
        'rest_framework.permissions.IsAuthenticated',
    ),
    'DEFAULT_AUTHENTICATION_CLASSES': (
       'rest_framework_jwt.authentication.JSONWebTokenAuthentication',
    ),
}
Next, make sure to import the following dependencies in your settings.py file:

import json
from six.moves.urllib import request
from cryptography.x509 import load_pem_x509_certificate
from cryptography.hazmat.backends import default_backend
Then, add the following code at the end of this file:

AUTH0_DOMAIN = '<YOUR_AUTH0_DOMAIN>'
API_IDENTIFIER = '<YOUR_API_IDENTIFIER>'
PUBLIC_KEY = None
JWT_ISSUER = None

if AUTH0_DOMAIN:
    jsonurl = request.urlopen('https://' + AUTH0_DOMAIN + '/.well-known/jwks.json')
    jwks = json.loads(jsonurl.read().decode('utf-8'))
    cert = '-----BEGIN CERTIFICATE-----\n' + jwks['keys'][0]['x5c'][0] + '\n-----END CERTIFICATE-----'
    certificate = load_pem_x509_certificate(cert.encode('utf-8'), default_backend())
    PUBLIC_KEY = certificate.public_key()
    JWT_ISSUER = 'https://' + AUTH0_DOMAIN + '/'


def jwt_get_username_from_payload_handler(payload):
    return 'auth0user'


JWT_AUTH = {
    'JWT_PAYLOAD_GET_USERNAME_HANDLER': jwt_get_username_from_payload_handler,
    'JWT_PUBLIC_KEY': PUBLIC_KEY,
    'JWT_ALGORITHM': 'RS256',
    'JWT_AUDIENCE': API_IDENTIFIER,
    'JWT_ISSUER': JWT_ISSUER,
    'JWT_AUTH_HEADER_PREFIX': 'Bearer',
}
Make sure to replace <YOUR_AUTH0_DOMAIN> with your own Auth0 domain and <YOUR_API_IDENTIFIER> with the identifier used while creating the Auth0 API.

The public key is retrieved from https://YOUR_AUTH0_DOMAIN/.well-known/jwks.json using the request.urlopen() method. This key is then assigned to PUBLIC_KEY in JWT_AUTH (the settings object for djangorestframework-jwt).

JWT_ISSUER is your Auth0 domain name prefixed by https.

JWT_ALGORITHM needs to be set to RS256. That means that you also need to make sure your Auth0 API is using RS256.

The JWT_AUTH_HEADER_PREFIX is set to Bearer. This is the default prefix used by most frameworks (djangorestframework-jwt uses a JWT prefix by default).

You also have set JWT_PAYLOAD_GET_USERNAME_HANDLER to a custom method. This tells djangorestframework-jwt to use your custom method in order to map the username from the access_token payload to the Django user.

For most cases, you don't need to store users in your database since Auth0 handles all of that for you including advanced features such as profiles. You can use a custom function that checks if a general (can be fake) user that you create exists and map it to all Auth0 users.

To do that, head over to your application and create a user with any valid username such as auth0user. You can do that through Django admin interface or in a migration by adding the following code:

# create an empty data migration
python manage.py makemigrations --empty catalog
This will generate the catalog/migrations/0001_initial.py file. In this file, you can replace the content with the following code:

from django.db import migrations
from django.conf import settings


def create_data(apps, schema_editor):
    User = apps.get_model(settings.AUTH_USER_MODEL)
    user = User(pk=1, username="auth0user", is_active=True , email="admin@techiediaries.com")
    user.save()


class Migration(migrations.Migration):
    dependencies = [
    ]
    operations = [
        migrations.RunPython(create_data),
    ]
For more information about migrations, see the official docs.

Next, just run migrate to create your initial data:

python manage.py migrate
This is the custom method that maps the JWT payload with the auth0user user:

def jwt_get_username_from_payload_handler(payload):
    return 'auth0user'
Please, note that you can return the username of any existing user in the database because you are not going to use this for anything besides the sole purpose of letting djangorestframework-jwt successfully authenticate the user.

## Adding Django Views
To make sure the JWT authentication via Auth0 is working, you can add these two view functions in catalog/views.py:

from rest_framework.decorators import api_view
from django.http import HttpResponse


def public(request):
    return HttpResponse("You don't need to be authenticated to see this")


@api_view(['GET'])
def private(request):
    return HttpResponse("You should not see this message if not authenticated!")
Also, make sure to create the corresponding URLs in urls.py. You can replace the whole contents of this file with this:

from django.conf.urls import url
from catalog import views


urlpatterns = [
    url(r'^api/public/', views.public),
    url(r'^api/private/', views.private)
]
If you rerun your Django project now (python manage.py runserver), you will have access only to the http://127.0.0.1:8000/api/public/ URL. The other one (/api/private/) will need an access token to be accessed.

Enabling CORS on Django
As you are going to create a Vue.js application to consume the Django endpoints, you will need to enable CORS on your Django project. To do that, you can install the django-cors-headers utility as follows:

pip install django-cors-headers
After that, you have to add this utility to your installed apps in the settings.py file:

INSTALLED_APPS = [
    # ...
    'corsheaders',
]
Then, you have to add the CorsMiddleware in this same file:

MIDDLEWARE = [
    # ...
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.common.CommonMiddleware',
]
The last thing you will need to do is to configure what origins will be accepted in your Django application:

CORS_ORIGIN_WHITELIST = (
    'localhost:8080',
)
You can add this configuration as the last item in the settings.py file.

## Integrating Auth0 with The Vue.js frontend
In this section, you will see how you can add Auth0 authentication to your frontend Vue.js application. You will also add a button to use the access token, retrieved from Auth0, to allow users to fetch the message from the /api/private/ endpoint.

Creating an Auth0 Client
To represent your Vue.js frontend application on Auth0, you will need to create an Auth0 client. To do that, go to your Auth0 dashboard and click on the New Client button.

You will be presented with a page where you can enter the name of the client and the type of the client. You can fill the name of the application as Django Vue.js App and choose the Single Page Web Applications type.

Creating an Auth0 Client

After filling this form, click on the Create button. This will redirect you to a page where you can find the Settings tab.

Configuring the Callback URL
You will need to whitelist the callback URL for your app (http://localhost:8080/) in the Allowed Callback URLs field of your new Auth0 client. This can be done in the Settings tab. In this tab, find the field mentioned and add http://localhost:8080/ to it. Then click on the Save button.

Creating the Authentication Service
Now. you will focus on integrating Auth0 in your Vue.js application. To do that, you will have to install the auth0.js and the eventemitter3 libraries:

# change directory to frontend
cd frontend

# install dependencies
npm install --save auth0-js eventemitter3
You also need to install Axios to send AJAX requests to the Django backend:

npm install --save axios
After installing these three dependencies, create a new file under ./frontend/src/auth/ (you will need to create the auth directory). You will call this file as AuthService.js and add the following code:

import auth0 from 'auth0-js'
import EventEmitter from 'eventemitter3'
import router from './../router'

export default class AuthService {
  authenticated = this.isAuthenticated()
  authNotifier = new EventEmitter()

  constructor () {
    this.login = this.login.bind(this)
    this.setSession = this.setSession.bind(this)
    this.logout = this.logout.bind(this)
    this.isAuthenticated = this.isAuthenticated.bind(this)
    this.handleAuthentication = this.handleAuthentication.bind(this)
  }

  // create an instance of auth0.WebAuth with your
  // API and Client credentials
  auth0 = new auth0.WebAuth({
    domain: '<YOUR_AUTH0_DOMAIN>',
    clientID: '<YOUR_CLIENT_ID>',
    redirectUri: '<YOUR_CALLBACK_URL>',
    audience: '<YOUR_AUDIENCE>',
    responseType: 'token id_token',
    scope: 'openid profile'
  })

  // this method calls the authorize() method
  // which triggers the Auth0 login page
  login () {
    this.auth0.authorize()
  }

  // this method calls the parseHash() method of Auth0
  // to get authentication information from the callback URL
  handleAuthentication () {
    this.auth0.parseHash((err, authResult) => {
      if (authResult && authResult.accessToken && authResult.idToken) {
        this.setSession(authResult)
      } else if (err) {
        console.log(err)
        alert(`Error: ${err.error}. Check the console for further details.`)
      }
      router.replace('/')
    })
  }

  // stores the user's access_token, id_token, and a time at
  // which the access_token will expire in the local storage
  setSession (authResult) {
    this.accessToken = authResult.accessToken
    this.idToken = authResult.idToken
    this.profile = authResult.idTokenPayload
    this.expiresAt = authResult.expiresIn * 1000 + new Date().getTime()
    this.authNotifier.emit('authChange', {authenticated: true})
  }

  // remove the access and ID tokens from the
  // local storage and emits the authChange event
  logout () {
    delete this.accessToken
    delete this.idToken
    delete this.expiresAt
    this.authNotifier.emit('authChange', false)
    // navigate to the home route
    router.replace('/')
  }

  // checks if the user is authenticated
  isAuthenticated () {
    // Check whether the current time is past the
    // access token's expiry time
    return new Date().getTime() < this.expiresAt
  }

  // a static method to get the access token
  getAuthToken () {
    return this.accessToken
  }

  // a method to get the User profile
  getUserProfile (cb) {
    return this.profile
  }
}
You will need to replace <YOUR_AUTH0_DOMAIN>, <YOUR_CLIENT_ID>, <YOUR_CALLBACK_URL>, and <YOUR_AUDIENCE> with the values from your client and API settings. The audience property refers to the identifier of your Auth0 API (i.e. if you followed the instructions, it will be https://django-vuejs-api).

Creating the Homepage
Now, you are going to refactor your Vue.js homepage to allow users to authenticate via Auth0 and to fetch public and private messages. To do that, open ./frontend/src/App.vue and replace the <template> code with this:

<template>
  <div>
    <button
      class="btn btn-primary btn-margin"
      v-if="!authenticated"
      @click="login()">
      Log In
    </button>

    <button
      class="btn btn-primary btn-margin"
      v-if="authenticated"
      @click="privateMessage()">
      Call Private
    </button>

    <button
      class="btn btn-primary btn-margin"
      v-if="authenticated"
      @click="logout()">
      Log Out
    </button>
    {{"{{ "}}{{ "message" }} }}
    <br>
  </div>
</template>
Creating the Methods
Still in your ./frontend/src/App.vue, replace the <script> tag with this:

<script>
import AuthService from './auth/AuthService'
import axios from 'axios'

const API_URL = 'http://localhost:8000'
</script>
This imports the AuthService from ./auth/AuthService and the axios library. After that, it declares the API_URL constant which holds the URL of the backend server.

After the API_URL constant, create an instance of AuthService:

const auth = new AuthService()
Then, below the auth definition, start defining the app component:

export default {
  name: 'app',
  data () {
    this.handleAuthentication()
    this.authenticated = false

    auth.authNotifier.on('authChange', authState => {
      this.authenticated = authState.authenticated
    })

    return {
      authenticated: false,
      message: ''
    }
  },
}
In this code, you are listening for the authChange event emitted by AuthService when the authentication state changes. You then assign the result to the authenticated variable. You also set the message variable to be empty. This variable will hold the response from your protected endpoint.

The last thing you need to do is to define the methods property of the app component:

export default {
  // name: 'app',
  // data () { ... },
  methods: {
    // this method calls the AuthService login() method
    login () {
      auth.login()
    },
    handleAuthentication () {
      auth.handleAuthentication()
    },
    logout () {
      auth.logout()
    },
    privateMessage () {
      const url = `${API_URL}/api/private/`
      return axios.get(url, {headers: {Authorization: `Bearer ${auth.getAuthToken()}`}}).then((response) => {
        console.log(response.data)
        this.message = response.data || ''
      })
    }
  }
}
The login(), handleAuthentication(), and logout() methods are simply wrappers for the corresponding methods in AuthService.

In the private() method, you are now using the axios.get() method to send a GET request to http://localhost:8000/api/private/. Since this endpoint is protected by Auth0, you also added an Authorization header. The access token is retrieved from the local storage using AuthService.getAuthToken() method.

## Testing the Django, Vue.js, and Auth0 Integration
Now that everything is correctly configured, you can test the integration among Django, Vue.js, and Auth0. To do that, go back to the root directory of your project and run the following commands:

# run Django in the background
python manage.py runserver &

# move to the frontend directory
cd frontend

# run Vue.js in the background &
npm run dev &
After running both the backend and the frontend projects, you can head to the Vue.js homepage (http://localhost:8080/) to test it.

In the homepage, you will see the Log In button. Clicking on it will redirect you to the Auth0 login page.

Auth0 login page

After authenticating, you will be redirected to your Vue.js application, where the Call Private and the Log Out buttons will appear. Clicking on the Call Private button will issue a GET request to the Django framework, alongside with an access token, and will fetch the secured message.


##  Authentication on Page Refresh
One thing you might notice is that, if you refresh the page in your browser, your user will be unauthenticated again. The problem here is that you are persisting user data (profile and tokens) in memory. To solve that, developers used to use localStorage. However, as this approach is not secure, you will be better off using another approach.

Luckily, Auth0 provides (through its auth0-js library) a method called checkSession that verifies if the current user has a valid session at Auth0. If they do, Auth0 then respond with the tokens you need in your app.

To use this method, you will first need to update a configuration property of your Auth0 Application. So, open the Auth0 dashboard, click in your app, and search for the Allowed Web Origins field. On this field, add the http://localhost:8080. Adding it will make Auth0 allow apps running on the localhost:8080 domain to use the checkSession method.

After inserting updating this setting, save the changes in your Auth0 Application and head back to your project. There, open the ./frontend/src/auth/AuthService.js file and update it as follows:
browser, you will see that your user will be authenticated again and that you can consume the private API.
