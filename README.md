# Wordpress to Jekyll project

Use Wordpress as a headless CMS-- hosted at a private subdomained Wordpress install
and hidden from search engines, users can login to Wordpress to add/update posts
and the Wordpress posts will be synced to a Jekyll site hosted on Netlify, CloudCannon
or a similar continuous deployment host to take advantage of static HTML pages and
constantly synced posts and content from Wordpress

### What you need

1. A Wordpress site hosted somewhere that can serve as a place for staff or editors
   to use an editorial workflow to create posts
   a. WP Plugins installed on your headless WP site: [WP-Markdown](https://wordpress.org/plugins/wp-markdown/), [WP Github Sync](https://wordpress.org/plugins/wp-github-sync/)
1. A free [github account](https://github.com/join)
1. A free [Netlify account](https://app.netlify.com/signup)

### Quick deploy to Netlify

Use the button below to deploy this site to netlify.  

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/shorelinemedia/shoreline-wp-to-jekyll)

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
