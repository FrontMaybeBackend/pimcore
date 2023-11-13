Hello,

if you want to tested this project, you need to copy URL repo
and open terminal in your IDE and paste link with command "git clone".


Another step is  enable required php extension  in php.ini :
open and delete ";" from extensions [extension=gd, extension=intl,zend_extension].

If you deleted semicolon from php.ini open IDE and in terminal write "composer install"
this comand will be downloand all packages to work this project.

enable xampp and start apache and mysql

Create DB in your local database

and write this command in terminal to configure it.
"php ./vendor/bin/pimcore-install"

![db](https://github.com/FrontMaybeBackend/pimcore/assets/109105280/ad661ca9-6a5e-47a5-b147-0b8133acf85c)


if you have configured db, now we must configured apache
Open httpd.config
find documentRoot and define path to your public catalog in project:

![documentRoot](https://github.com/FrontMaybeBackend/pimcore/assets/109105280/a88a3b87-a04e-417f-b0e4-b56f5c53cd4c)

 
you can open frontend in  browser, write "localhost"
admin panel with localhost/admin.
to login you need data from this:
![image](https://github.com/FrontMaybeBackend/pimcore/assets/109105280/3418a123-e6d0-4bd9-b439-edb1cdd10e63)


if you didnt see data importer in gui go to terminal and install:

php bin/console pimcore:bundle:install PimcoreDataHubBundle
and
php bin/console pimcore:bundle:install PimcoreDataImporterBundle


If you want import files click dataImport in the left bar 
![import](https://github.com/FrontMaybeBackend/pimcore/assets/109105280/8fbfeb1d-2988-4c13-b4b1-0045b038ee72)
and select import which are you interested.

Upload file and go to the Execution:
![select](https://github.com/FrontMaybeBackend/pimcore/assets/109105280/4ec38af9-4c9e-418e-b67e-e3c0a68322eb)

Click start:
and go to your path in project in terminal (cmd):
e.g
C:\xampp\htdocs\test\pimcore>
and write 
php bin/console datahub:data-importer:process-queue-sequential
and you will see a process were files are uploading.

After uploading you can go to home in DataObcjets and saw your data.

Good luck :)
