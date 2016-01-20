# Zodiac Media Drupal 8 Skeleton

This skeleton project is the foundation for migrating your Drupal 7 site to Drupal 8. This guide assumes that you are using a Macintosh or Linux system and have knowledge of the command line.

## Instructions

### Step 1 - Download the Project

As Drupal 8 is a major version jump from Drupal 7 the easiest way to get started is going to be create a new projects (and repository) for your newly upgraded site. We have created a Drupal migration skeleton to make life easier when migrating to Drupal 8, this utilises Vagrant ([vagrantup.com](https://www.vagrantup.com/)) and PuPHPet ([puphpet.com](https://puphpet.com/)).

So to get started clone the project into a folder on your hard drive,

```
git clone https://github.com/zodiacmedia/drupal8-migration-skeleton.git new-drupal-project
```

Once done, you may want to update the version of Drupal in the application folder. You can get the latest version from the Drupal website ([drupal.org/download](https://www.drupal.org/download)).


### Step 2 - Get your old database

The next step is to get your old database and to copy it into the project file. The best route to do this is to go to your server and enter this command.

```
mysqldump -uroot -p123 zodiacmedia > database.sql
```

**root** should be replaced with your mysql username, **123** should be replaced with your mysql username and **zodiacmedia** should be replaced with your database name. If you don’t know this information, you should be able to get it by going to **/sites/default/settings.php** in your Drupal 7 installation.

Once complete, copy the database.sql file to the _database folder of the Drupal 8 skeleton project. You will then need to edit **/vagrant/puhpet/config.yaml** and edit line **322** to match your database name.

### Step 3 - Setup Vagrant

Next, you will need to go on the command line to the project root and then the vagrant folder (make sure that you have installed vagrant before doing this). Enter the following command,