install django django-crispy-forms  = will let us style all out bootstrap forms automatically
install stripe = pip3 install stripe
export STRIPE_PUBLIC_KEY = ''
export STRIPE_SECRET_KEY = ''
install counrty codes = pip3 install django-countries
pip3 freeze > requirements.txt
to add a new app = python3 manage.py startapp profiles
to load data from products = python3 manage.py loaddata products

To deploy from heroku 
make app in heroku
provion a heroku postgres
database for heroku = pip3 install dj_database_url
also = pip3 install psycopg2-binary

set up databse in settings.py
import dj_database_url

go to heroku and then get the postgres url from config vars and put it in the defult dtabse in settings.py
then check with python3 manage.py showmigrations
then python3 manage.py migrate

Categories has to be done first
then load the data from the items = python3 manage.py loaddata categories
then the same for products =python3 manage.py loaddata products
Then create a superuser python3 manage.py createsuperuser 

then remove the database stuff and put back the default to it does not endup in version control

install green unicorn = pip3 install gunicorn

again
pip3 freeze > requirements.txt

create Procfile
with web: gunicorn boutique_ado.wsgi:application

Last we need to temporarily disable collectstatic. By using Heroku config set, disable collectstatic equals 1
So that Heroku won't try to collect static files when we deploy.

heroku config:set DISABLE_COLLECTSTATIC=1 --app jonathanw82-boutique-ado

 we'll need to add the hostname of our Heroku app to allowed hosts in settings.py
 ALLOWED_HOSTS = ['jonathanw82-boutique-ado.herokuapp.com', 'localhost'] added local host so gitpod will work aswell

push to heoku 

dont foregt to remove secret key

install some more packages
pip3 install boto3
pip3 install django-storages