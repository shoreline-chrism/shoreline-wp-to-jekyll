# Site Maintenance website

Should our site or client website's server go down for an extended period or is
down without an ETA on restoration we can quickly launch this website
maintenance page hosted on Netlify and 302 redirect the primary domain to this
maintenance site until the issues are resolved.

### What you need

1. A free [github account](https://github.com/join)
1. A free [Netlify account](https://app.netlify.com/signup)

### Quick deploy to Netlify

Use the button below to deploy this site to netlify.  Before you deploy you can
set environment variables for things like the logo url, primary color,
background color, client name, etc.

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/shorelinemedia/shoreline-maintenance)

### Adding a logo

Before deploying, uploading a logo to imgur.com might be a quick way to get logo image on the web
and not being served from the affected server. Once you upload to imgur, grab the
ID of the image and change the logo url to `//i.imgur.com/YOURID.extension`
and change YOURID to the imgur ID and the `.extension` to `.png`, `.jpg`, etc

If you don't have a logo that is publicly accessible during your initial deploy
to netlify, you can add a logo to this site/project directly:

1. After initial deployment on netlify, netlify creates a copy of the project in
   in your github account. Login to your github account and visit the project at
   [github.com](http://github.com)
1. Navigate to the `/assets/uploads/` folder on gitub and click the *Upload files* button
1. Upload a logo to this folder (We'll assume it's `logo.png`)
    a. Adding a file to your repository on github will trigger a build on Netlify
       which makes it available on your website in just a few minutes.
1. Login to [Netlify](https://app.netlify.com) and click your maintenance site
1. Navigate to *Settings* tab if you aren't there already
1. Edit the *Build Environment* settings and update the SL9_CUSTOM_LOGO to your
   new logo url: `/assets/uploads/logo.png`
1. Goto *Deploys* tab on netlify and click *Trigger Build* which will trigger a new
   build using your new logo url

#### Development

To develop this site with Jekyll [read the development notes](develop.md).
