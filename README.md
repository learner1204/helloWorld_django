# Django Hello world Project

## Steps to follow:

1. install virtual environment

    ```
    pip install virtualenv
    ```

2. create virtual environment

    ```
    virtualenv venv
    ```

3. Activate virtual environment

    ```
    venv\Scripts\.\activate
    ```

4. install django

    ```
    pip install django
    ```

5. check version of django

    ```
    django-admin --version
    ```

6. create django project

    ```
    django-admin startproject projectName
    ```

7. create django app

- go inside project 

    ```
    cd projectName
    ```

- and run following code

    ```
    django-admin startapp AppName
    ```

8. Tell project that a new app is created

- go to projectName > settings.py > INSTALLED_APPS and add your AppName in the list

9. open views.py and type the following:

    ```python
    from django.http import HttpResponse

    # Create your views here.
    def sayHello(request):
        return HttpResponse('<h1 style="color:red">Hello World!</h1>')
    ```

10. go to your project folder > urls.py and add following:

    ```py
    from django.urls import path,include

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('',include('AppName.urls')),
    ]
    ```

11. next step

- copy paste urls.py from your project folder to your app folder
- delete all previous code and then paste the following:

    ```py
    from django.urls import path,include
    from .views import sayHello

    urlpatterns = [
        path('',sayHello,name='sayHello'),
    ]
    ```

12. Run the server

    ```py
    python manage.py runserver
    ```

13. close running server

    press ctrl+c

14. To deactivate virtual environment, hit the following in terminal

    ```
    deactivate
    ```
