# Jekbox

Jekbox uses Dropbox and Jekyll to automatically create and serve sites based on folders in your
Dropbox that are named using a domain name. For example, if you place a folder in your Dropbox
named `www.nicesite.com` then Jekbox will build the contents with Jekyll and respond to all
requests to the `www.nicesite.com` by serving the contents of that folder.

Sites are served by Jekyll's default server (`jekyll server`), which also watches
for any changes to your site and automatically rebuilds. The Jekyll servers sit behind a simple
reverse proxy, so you can have multiple sites on one Jekbox installation.

One benefit of hosting sites from your Dropbox folder is that you can share the folders with other
people. So, if you're making a website for a friend or a client, they can edit they're site simply
by changing files in their personal Dropbox folder.

## Installation
`docker pull tombh/jekbox`

##Usage
`docker run --restart always --publish 80:80 --name jekbox jekbox`

On first installation you will be asked to connect your Dropbox account. Watch the logs for the
link to connect your account to Jekbox.

You will also need to make sure that the DNS for your site, eg `www.nicesite.com` points to the
server on which Jekbox is installed.

Jexbox does not currently support wildcard domains, eg; `*.nicesite.com`.

##TODO
Instructions for using a data container to persist Dropbox setup. All it will mean is that you don't
have to link your account every time.

Or maybe even automate the browser connection flow using Nokogiri. That way your Dropbox username
and pasword could be provided as ENV vars and you wouldn't have to manually make the connection
every time.
