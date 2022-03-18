# Apache-superset-deploy-heroku
One-button Heroku deploy for the Apache Superset data exploration platform. 

# [superset](https://github.com/airbnb/superset) on [Heroku](http://heroku.com)

Superset is a data exploration platform designed to be visual, intuitive, and interactive. Visit the project's website at <http://airbnb.io/superset>

## Deploying on Heroku

To get your own Superset App running on Heroku, click the button below:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/sidiber/Apache-superset-deploy-heroku)

Fill out the form, and later you should be performing analytics at the speed of thought.

### Things you should know
##### After deployment

- Superset will be accessible at `YOURAPPNAME.herokuapp.com`.

- To make changes to your app like creating admin user, clone your app locally using the [Heroku Toolbelt](https://toolbelt.heroku.com/):

```sh
heroku git:clone --app YOURAPPNAME
```
It will be reported as empty "warning: Vous semblez avoir cloné un dépôt vide." - that's ok.
- Pull the remote main
```sh
cd YOURAPPNAME
git remote add origin https://github.com/sidiber/Apache-superset-deploy-heroku
git pull origin main
```
You will normally retrieve all the contents of your git

- Create an Admin user by using

```sh
heroku run bash --app YOURAPPNAME
export FLASK_APP=superset
superset fab create-admin
superset db upgrade
superset init
exit
```
- Make changes
- Clone the repository
```sh
heroku login
heroku git:clone -a YOURAPPNAME
cd YOURAPPNAME
```
You can make the changes you want
-Deploy your changes

```sh
git add .
git commit -m "make it better"
git push heroku master
```

- Check Papertrail logs for debugging any errors.

### How this works

This repository is essentially a minimal web application that specifies [Superset as a dependency](https://github.com/airbnb/superset), and makes a deploy button available.

## Problems?
If you have problems with the deployment, you can check [SETTING UP APACHE SUPERSET ON HEROKU](https://chizurumolorondu.medium.com/setting-up-apache-superset-on-heroku-b547302f600e)

If you have problems using your instance of Superset, you should check the [official documentation](http://airbnb.io/superset/installation) or open an issue on [issue tracker](https://github.com/airbnb/superset/issues). If you discover an issue with the deployment process provided by *this repository*, then [open an issue here](https://github.com/neevany/caravel-on-heroku/issues).

