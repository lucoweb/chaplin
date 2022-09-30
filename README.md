# Chaplin
An example movie catalog with Drupal 9 built using DDEV.

# Prerequisites
1. Windows users:
   1. WSL2
   2. Docker
   3. Ubuntu for Windows
   4. [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-us&gl=us) recommended.
2. Linux/Mac OS
   1. Docker

*Please note:* This setup was not tested in either Linux or Mac OS. YMMV.

# Usage
- Clean installation strongly advised.
- Import the DB dump provided or run ```drush cim``` to import the config sync files from **sites/default/files/sync**.
- place the Movies/Actors images in:
  - sites/default/files/actors
  - sites/default/files/movies
- Unpack the custom theme *Theater* and place it in **themes/custom**.
- login with username/password: ```admin```

# Installing DDEV

***Please note:*** If you're following any of the steps below, keep a backup of the repository files.

The command ```ddev config --project-type=drupal9 --docroot=web --create-docroot``` will erase: 
- all of the content images;
- DB dump;
- config sync files; and
- the custom theme.

- Please run the following commands, line per line, and enter admin password if needed:
```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install build-essential apt-transport-https ca-certificates software-properties-common curl
$ curl -O https://raw.githubusercontent.com/drud/ddev/master/scripts/install_ddev.sh
$ chmod +x install_ddev.sh
$ ./install_ddev.sh
$ mkdir -p ~/projects/chaplin
$ cd ~/projects/chaplin
$ ddev config --project-type=drupal9 --docroot=web --create-docroot
$ ddev start
$ ddev composer create "drupal/recommended-project"
$ ddev composer require drush/drush drupal/admin_toolbar drupal/devel:^5.0@beta drupal/admin_toolbar drupal/bootstrap_barrio drupal/bootstrap_sass
$ ddev exec drush site:install --account-name=admin --account-pass=admin
$ chmod 555 web/sites/default
$ chmod 444 web/sites/default/settings.php
```

- Visit your local site at: https://chaplin.ddev.site
- Start the container with ```ddev start```
- Stop the container with ```ddev stop```

# Compiling the theme

```
$ sudo apt install curl
$ curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
$ source ~/.profile
$ nvm install node
$ cd ~/projects/chaplin/web/themes/custom/theater/
$ npm install --global gulp-cli
$ npm install
$ gulp
```

*Please note:* 
- The theme was already compiled to speed up screening.
- The ```gulp``` command keeps running, so you don't need to re-run it. Simply make changes to SCSS files and refresh your browser.
