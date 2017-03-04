### Dependencies

* Oracle VM Virtualbox
* Vagrant (http://vagrantup.com)

### Dev

1. Clone Repo into `~/yourprojectdir` (change yourprojectdir)
2. Change into directory `cd ~/yourprojectdir`
3. Bring up VM and install dependencies with `vagrant up`
4. SSH into server: `vagrant ssh`
5. Change director to /vagrant and run develop shell script:
````
cd /vagrant && ./develop.sh
````

### Quick deploy to Netlify

Use the button below to deploy this site to netlify

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/shorelinemedia/shoreline-maintenance)

### Environment Variables
We use environment variables to quickly fill in logo and client information when
working locally or deploying to netlify.  The `develop.sh` script applies these
automatically.

Here is a list of current environment variables you can set locally or when deploying
to Netlify

* CLIENT_NAME = "Shoreline Media Marketing"
* CUSTOM_LOGO = "//shorelinemedia.github.io/images/Shoreline-Media1.neuquant.png"
* PRIMARY_COLOR = "#0099CC"
* BG_COLOR = "#587E9D"
* UP_MESSAGE = "`<p>We are upgrading our website.  We'll be back online shortly.</p>`"
* SL9_MAINTENANCE_MESSAGE = "We are currently upgrading our website"
