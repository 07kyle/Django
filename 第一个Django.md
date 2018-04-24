##  python虚拟环境--virtualenv
`virtualenv `是一个创建隔绝的`Python`环境的工具。`virtualenv`创建一个包含所有必要的可执行文件的文件夹，用来使用Python工程所需的包.

 **window安装**
> pip install virtualenv 或 pip3 install virtualenv

**Linux和Mac安装**
>  sudo pip install virtualenv  或 sudo pip3 install virtualenv

**测试是否安装成功**
> virtualenv --version
15.1.0

## 创建虚拟环境
下面以window为例，创建一个python3的虚拟环境。
假设在E盘已经有一个工程目录env，进入工程目录中，执行以下命令：
> C:\Users\Administrator>e:
E:\>cd env
E:\env>virtualenv kyle
Using base prefix 'c:\\users\\administrator\\appdata\\local\\programs\\python\\python36-32
New python executable in E:\env\kyle\Scripts\python.exe
Installing setuptools, pip, wheel...done.

现在，virtualenv为我们在工程目录env中，创建了一个名为kyle的子目录，它里面保存了一个全新的虚拟环境，非常简单。

## 激活和退出虚拟环境
在使用虚拟环境之前，必须将其激活，命令如下：
> E:\env>cd kyle
E:\env\kyle>cd Scripts
E:\env\kyle\Scripts>activate

这时，可以看到shell提示符前面加上了(venv)前缀，说明已经工作在虚拟环境之下了
> (kyle) E:\env\kyle\Scripts>

退出虚拟环境只要执行：
> (kyle) E:\env\kyle\Scripts>deactivate

##在虚拟环境中安装Django
> E:\env\testenv\Scripts>pip install django==1.11

##在E盘目录的project文件夹创建第一个Django项目
> E:\env\testenv\Scripts>activate
(testenv) E:\env\testenv\Scripts>cd ..
(testenv) E:\env\testenv>cd ..
(testenv) E:\env>cd ..
(testenv) E:\>django-admin startproject hello #(项目名称)

##启动manage.py
> (testenv) E:\>cd hello
(testenv) E:\hello>python manage.py 
Type 'manage.py help <subcommand>' for help on a specific subcommand.
Available subcommands:
[auth]
changepassword
createsuperuser
[contenttypes]
remove_stale_contenttypes
[django]
 check
 compilemessages
 createcachetable
dbshell
diffsettings
dumpdata
flush
inspectdb
loaddata
makemessages
makemigrations
migrate
sendtestemail
shell
showmigrations
sqlflush
sqlmigrate
sqlsequencereset
squashmigrations
startapp
startproject
test
testserver
[sessions]
clearsessions
[staticfiles]
collectstatic
findstatic
runserver

##启动项目
>  (kyle) E:\hello>python manage.py runserver
Performing system checks...
System check identified no issues (0 silenced).
You have 13 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin,
 auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
April 23, 2018 - 12:39:36
Django version 1.11, using settings 'hello.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.

如果看到这样了，那么恭喜你，你的第一个由Django的驱动的页面正常工作了
