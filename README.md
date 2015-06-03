Vagrant Bootstrap project
====================
A basic install of ubuntu/trusty64 stack plus additional install of apache, MySql and PHP using bash script.

What will you get:
-----------------
- apache 2.5
- php 5.5
- mysql
- phpmyadmin
- xDebug
- enabled mod_rewrite
- virtual host
- increased post_max_size, upload_max_filesize, ect.
- git
- Composer

Usage:
------------
Let's assume that you have [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html) installed.

Install the dependency plugin hostmanager:

    $ vagrant plugin install vagrant-hostmanager

Clone the repo:

    $ git clone https://github.com/isBatak/vagrant_bootstrap.git

Adjust the info in Vagrantfile:

    box         = 'ubuntu/trusty64' //change at your own risk
    projectname = 'projectname'
    hostname    = projectname + '-hostname'
    domain      = '.dev'

Adjust the info in bootstrap.sh:

    PASSWORD='root'
    PROJECTFOLDER='public'

Navigate to folder containing Vagrantfile and run:

    $ vagrant up

Now, If everything was done correctly you will have 'public' folder (PROJECT FOLDER name in bootstrap.sh) and the site will be accessible at the projectname.dev (projectname + domain in Vagrantfile settings). Currently you'll only see .log files but if you copy your website in 'public' folder and setup database you'll have a functional site.

For Windows users
-----------------
If hostmanager detects that it cannot overwrite the file, it will attempt to do so with elevated privileges, causing the UAC prompt to appear.
