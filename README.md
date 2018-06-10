![manalogo](http://7xj431.com1.z0.glb.clouddn.com/1459330965_869446.png)
==
<hr/>

### the missing startproject command for Flask, simple & fast <br/>

[![Github All Releases](https://img.shields.io/github/downloads/atom/atom/total.svg?style=social)](https://github.com/misakar/mana)

[![PyPI](https://img.shields.io/pypi/v/mana.svg)](https://pypi.python.org/pypi/mana)
<br/>

## What is mana
mana is just like Django startproject command, it helps you  build and manage your flask project swiftly with litte effort!

## [Mana GIF Demo](https://camo.githubusercontent.com/515963f2335abbc45ba523be69e0d09e517b64e1/687474703a2f2f37786a3433312e636f6d312e7a302e676c622e636c6f7564646e2e636f6d2f6d616e616d616e616d616e612e676966)

## mana command sets
### => mana startproject (project_name)
**mana startproject** command is powerful, it can help you build a SQL database driven project, and provides a CRUD admin dashboard.
#### mana startproject (project_name)

    $ mana startproject myblog

This commmand creates a flask project called myblog, and its structure looks like this:

    myblog/ => requirement.txt
               manage.py
               config.py

               app/ => __init__.py
                       models.py
                       templates/ => main/
                                     auth/
                                     admin/
                       static/ => img/
                                  css/
                                  js/
                       admin/
                       auth/
                       main/ => __init__.py --
                                forms.py     |__ [you can writing your code here]
                                views.py --- |

#### install flask extensions

    $ virtualenv myblog_venv
    $ source myblog_venv/bin/activate  (Windows: venv\Scripts\activate)
    $ pip install -r requirement.txt

#### setup sql database
(mana use sqlite3 by default, you can switch this by editing config.py)

    $ python manage.py db init
    $ python manage.py db migrate
    $ python manage.py db upgrade

Create user roles

    $ python manage.py shell
    >> Role.insert_roles()
    >> quit()

#### create admin user

    $ python manage.py admin
    \_admin username:
    \_admin email:
    \_admin password:

#### run the project
Now, you can run myblog:

    $ python manage.py runserver

And open http://127.0.0.1:5000/admin in the browser, you can see the
DebugToolbar<br/>
![admin login](http://7xj431.com1.z0.glb.clouddn.com/manalogin4)<br/>

After log in as administrator, you can see the CRUD admin dashboard: <br/>
![admin site](http://7xj431.com1.z0.glb.clouddn.com/manaadmin22) <br/>
![admin site2](http://7xj431.com1.z0.glb.clouddn.com/manaadmin222)<br/>

### => mana admin (sql module_name)
<strong>mana admin</strong> command can add sql modules into admin site<br/>

### => mana blueprint (blueprint_name)
<strong>mana blueprint</strong> command can automatically create and
register a flask blueprint, go to the app folder:

    $ mana blueprint book

And the book blueprint is created and registed in <code>app/__init__.py</code>.

### => mana init (project_name)
<strong>mana init</strong> command can build a minimal flask app instantly. The project structure looks like this:

![mana init](http://7xj431.com1.z0.glb.clouddn.com/manainit) <br/>
After init, you should install flask extensions(I highly recommend using [virtualenv](http://flask.pocoo.org/docs/0.10/installation/#virtualenv)), just type <code>$ pip install -r requirement.txt</code> <br/>
And you can run your project using <code>$ python manage.py runserver</code> <br/>
Now, you can goto http://127.0.0.1:5000/test and check if everything is ok :)

### => mana version
Show the version info: latest version: 4.9

### => mana rest_startproject (project_name)
quick start a flask restful project.

## Install mana
#### 1. install by pip

    $ pip install mana

#### 2. install from source

    $ git clone https://github.com/neo1218/mana
    $ cd mana
    $ sudo pip install .

## flask extensions used by mana
### management

+ Flask-Script

### sql database

+ Flask-Migrate
+ Flask-Sqlalchemy

### auth

+ Flask-Login

### form

+ Flask-WTF

### admin

+ Flask-Admin

### debug

+ Flask-DebugToolbar

## UnitTest...

> test, test, test

    $ git clone https://github.com/neo1218/mana
    $ cd mana
    $ python test_mana.py

## Powered by Click
click: https://github.com/mitsuhiko/click

## LICENSE
MIT: check [LICENSE](https://github.com/neo1218/mana/blob/master/LICENSE) for more detail

## Change Logs

+ ***20160217***
    + v4.5
    - 让help信息更有用

+ ***20160306***
    + v4.6
    - 精简部分help信息
    - 添加Flask-DebugToolbar

+ ***20160326***
    + v4.7
    - 默认将Role数据加入admin site

+ ***20160327***
    + v4.8
    - haha:)

+ ***20180608***
    + v4.9
    - add `rest_startproject` and `rest_add_resource` command