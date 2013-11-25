What is it?
===========

If you want to install Django LFS [http://www.getlfs.com/] with facebook support, you can fork this repository.

How to use it?
==============

* git clone https://github.com/filippo91/lfs_facebook_buildout.git
* cd lfs_facebook_buildout/lfs-installer 
* virtualenv --no-site-packages . 
* bin/pip install --upgrade setuptools
* bin/python bootstrap.py
* facebook settings
  * You have to modify settings.py, where you are going to put right data for these variables:
    ```

      FACEBOOK_APP_ID = 'YOUR APP ID'
      FACEBOOK_APP_SECRET = 'YOUR APP SECRET NUMBER'

      FACEBOOK_PAGE = 'YOUR PAGE ID'

      #view that required a logged user
      VIEW_WITH_LOGIN_REQUIRED = {
        'add-to-cart': '' #True or False,
        'shop': '' #True or False,
        'category': '' #True or False,
        'product': '' #True or False,
        'checkout': '' #True or False,
      }
      
    ```
* bin/buildout -v
* bin/django syncdb
* bin/django lfs_init
* bin/django collectstatic
* bin/django runserver

More information
==============

* https://pypi.python.org/pypi/django-facebook
* http://www.getlfs.com/
* http://blog.pythonanywhere.com/35/
