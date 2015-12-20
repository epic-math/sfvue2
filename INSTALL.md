#Installation Instructions

*Make sure you have Python2.7.3, virtualenv, pip and sqlite3 installed*

1. Download or clone this repo.
2. Go to project home folder and run these commands:

    cp sfvue/example_local.py sfvue/local_settings.py 
    virtualenv venv 
    source venv/bin/activate 

3. This will create a virtual environment and activate it. Now use pip to install dependencies with:

    (note) We may want to install mariadb-devel to avoid 
           vertualenv EnvironmentError: mysql_config not found

    pip install -r dev-requirements.txt
    (note) 
       --allow-external PIL --allow-unverified PIL PIL==1.1.7

4. Now we have to prepare a database:

    python manage.py syncdb

5. It will ask you to provide username, email and password. Give them and run following migrations:

    python manage.py migrate guardian 
    python manage.py migrate resources 
    python manage.py migrate profiles 

5. Run django server 
    python manage.py runserver 

6. Go to [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

7. Create Resource Types named Book, Ebook, Tutorial, Online Course, Other.

8. Go to home page.

9. (note) SECRET_KEY is in local_settings.py, and this should not be committed. 
   Current KEY in settings.py is not used.
