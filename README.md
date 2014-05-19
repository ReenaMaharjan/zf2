zf2
====

Getting started: A skeleton application¶

In order to build our application, we will start with the ZendSkeletonApplication available on github. Use Composer (http://getcomposer.org) to create a new project from scratch with Zend Framework:

php composer.phar create-project --repository-url="http://packages.zendframework.com" zendframework/skeleton-application path/to/install


Alternately, clone the repository and manually invoke composer using the shipped composer.phar:

cd my/project/dir
git clone git://github.com/zendframework/ZendSkeletonApplication.git
cd ZendSkeletonApplication
php composer.phar self-update
php composer.phar install

(The self-update directive is to ensure you have an up-to-date composer.phar available.)

Another alternative for downloading the project is to grab it via curl, and then pass it to tar:

cd my/project/dir
curl -#L https://github.com/zendframework/ZendSkeletonApplication/tarball/master | tar xz --strip-components=1



Virtual Host

To setup apache virtual host to point to the public/ directory of the project and you should be ready to go! It should look something like below:

<VirtualHost *:80>
    ServerName zf2-tutorial.localhost
    DocumentRoot /path/to/zf2-tutorial/public
    SetEnv APPLICATION_ENV "development"
    <Directory /path/to/zf2-tutorial/public>
        DirectoryIndex index.php
        AllowOverride All
        Order allow,deny
        Allow from all
    </Directory>
</VirtualHost>

Make sure that you update your /etc/hosts or c:\windows\system32\drivers\etc\hosts file so that zf2-tutorial.localhost is mapped to 127.0.0.1. The website can then be accessed using http://zf2-tutorial.localhost.

127.0.0.1               zf2-tutorial.localhost localhost




