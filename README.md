# Craft CMS Site and Server Configuration

Prerequisites for this Guide:

* MAMP Pro Installed, using `htdocs/` folder as virtual hosts folder.

* [Composer](https://docs.craftcms.com/v3/installation.html#downloading-with-composer) is installed.

* Active [Laravel Forge](https://forge.laravel.com/) Account.

* Active [Digitalocean](https://www.digitalocean.com/) Account.

* [Bitbucket Account](https://bitbucket.org/)

## Local Build: Create Site

* Create Craft project within the `htdocs/` directory by using `$ composer create-project craftcms/craft <Project Name>` per [Craft CMS Installation Notes](https://docs.craftcms.com/v3/installation.html#step-1-download-craft) 

### MAMP Setup

* Create New Host, name host, assign `<Project Root>/ web` as the root folder, create database with host.

* Save, Restart MAMP servers.


### From Project Root

* Edit `.env` file to add database name, username and password.

* Follow instructions in [Craft CMS Boilerplate](https://github.com/bgcbrianclark/craftcms-biolerplate)

* Build Site.

* Version Control with Bitbucket.

## Server Setup

* Provision New Digitalocean Server with Forge. Add new Site.

* Add Domain Record to new IP.

* Add/Deploy Git Repository to Forge Site.

* FTP files from local to remote:

   * `web/uploads`
   * `/.env` (Update with Server specific username/passwords)

* From project root: `$ composer update`

* Add `/storage` folder.

* Set Craft Permissions, from Project Root: `$ sudo chmod -R 775 .env composer.json composer.lock config/license.key config/project.yaml storage/ vendor/ web/cpresources/`

* Test Site.
