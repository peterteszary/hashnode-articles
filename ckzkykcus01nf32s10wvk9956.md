---
title: "WordPress Development Environment on Pop OS"
datePublished: Sun Feb 13 2022 07:40:43 GMT+0000 (Coordinated Universal Time)
cuid: ckzkykcus01nf32s10wvk9956
slug: wordpress-development-environment-on-pop-os
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643539096670/oLwDHYpwx.jpeg
tags: wordpress-plugins, wordpress-themes, wordpress, developer

---

> The devil is in the small details...

So reflecting on my previous article (WordPress Boiler Plate Chase), I might find some solution to it. Also, it has a short story, that has happened this weekend. 

So previously I've started to breathe life into Sage's boilerplate, with no luck. I thought it was some specialized dependency problem, that was caused by Pop OS. So I decided to look into a different way for no, cause I want to make some progress. I'll get back to is when I am feeling comfortable with packages and dependencies like composer and node. 

VS Code extensions are not working

I found a [Tailwind boilerplate](https://github.com/jeffreyvr/tailpress) which looks good, and it was easy to install (I thought). BUT. Then I've wanted to install the Tailwind CSS Intellisense extension to my VS Code, because I am a bit lazy with remembering CSS classes, so it might help. I am using Tailwind with my WordPress projects, and I really like it, but it is easier to cheat a bit with a classes-helper like that. 

Ao after the installation an error message came up.

> Tailwind CSS: Can't resolve 'lodash' in ....

Or something like that. I've tried to get it back from my browser history, but It was just too many records. Anyways, I could not find the answer. But. I thought that might be a problem with Pop Os again. I've tried to uninstall, and reinstall Nodejs & npm again. Auto removes, purge and clear everything with an auto fix as well. Nothing worked. So I thought I will install the good old Ubuntu on my laptop again (the problems above were on my desktop PC). 

I have installed ubuntu beside my Pop Os, cause I did not want to go through the install processes of each Os week after week. I have installed 20.04 of Ubuntu, unfortunately. I did not check the version on the bootable Pendrive. So I had to upgrade after installation. 

Years passed while the terminal was updating the stuff. I decided to watch the Shang-Chi movie, and come back in the morning. In the morning everything was fine. I have installed Nodejs and npm. I have installed Local by Flywheel (as I told you I am lazy) and VS code (and also some Ubuntu tweaks).  Fresh WordPress install with the TailPress theme/repo in it. Great. Almost everything is green. Even the npm watch is working!!!

Then I wanted to install Tailwind CSS Intellisense with this fresh installation. Same error as previously. I made a coffee.

So the problem might not be with Ubuntu or Pop Os either. After some investigation, I have found the right solution with the right installation methods. I will create a Shell script later on and update the post with it. 

First of all, you have to clear all that you (probably) have done, to solve the problem.

[Source](https://support.system76.com/articles/package-manager-pop/)


# CLEAR EVERYTHING


```
sudo apt clean
sudo apt update -m
sudo dpkg --configure -a
sudo apt install -f
sudo apt full-upgrade
sudo apt autoremove --purge

``` 

## THEN


```
sudo apt install pop-desktop

``` 

## Removing Nodejs and Npm
[Source](https://stackoverflow.com/questions/32426601/how-can-i-completely-uninstall-nodejs-npm-and-node-in-ubuntu)

```
sudo apt-get remove nodejs npm node
sudo apt-get purge nodejs

``` 

## Now remove .node and .npm folders from your system

```
sudo rm -rf /usr/local/bin/npm 
sudo rm -rf /usr/local/share/man/man1/node* 
sudo rm -rf /usr/local/lib/dtrace/node.d 
sudo rm -rf ~/.npm 
sudo rm -rf ~/.node-gyp 
sudo rm -rf /opt/local/bin/node 
sudo rm -rf opt/local/include/node 
sudo rm -rf /opt/local/lib/node_modules  

sudo rm -rf /usr/local/lib/node*
sudo rm -rf /usr/local/include/node*
sudo rm -rf /usr/local/bin/node*
``` 

Go to home directory and remove any node or node_modules directory, if exists.

You can verify your uninstallation by these commands; they should not output anything.


```
which node
which nodejs
which npm

``` 

### And now, start it over, but first of all with Composer

NOTE: YOU HAVE TO INSTALL ALL THE FOLLOWING GLOBALLY!

So, not from VS Code's terminal in the theme folder of your WordPress theme

### Like this 

[Source](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04)


### Installing PHP and Additional Dependencies

First, update the package manager cache by running


```
sudo apt update

``` 

Next, run the following command to install the required packages:

```
sudo apt install php-cli unzip

``` 

### Downloading and Installing Composer


```
cd ~

``` 


```
curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php

``` 

Next, we’ll verify that the downloaded installer matches the SHA-384 hash for the latest installer found on the Composer Public Keys / Signatures page. To facilitate the verification step, you can use the following command to programmatically obtain the latest hash from the Composer page and store it in a shell variable:

```
HASH=`curl -sS https://composer.github.io/installer.sig`

``` 

If you want to verify the obtained value, you can run:


```
echo $HASH

``` 


```
Output
e0012edf3e80b6978849f5eff0d4b4e4c79ff1609dd1e613307e16318854d24ae64f26d17af3ef0bf7cfb710ca74755a

``` 

Now execute the following PHP code, as provided in the Composer download page, to verify that the installation script is safe to run:


```
php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

``` 

You’ll see the following output:

```
Installer verified

``` 

To install composer globally, use the following command which will download and install Composer as a system-wide command named composer, under /usr/local/bin:


```
sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer

``` 

You’ll see output similar to this:

```
Output
All settings correct for using Composer
Downloading...

Composer (version 1.10.5) successfully installed to: /usr/local/bin/composer
Use it: php /usr/local/bin/composer

``` 

To test your installation, run:


```
composer

``` 

Output:


```
Output
   ______
  / ____/___  ____ ___  ____  ____  ________  _____
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/
                    /_/
Composer version 1.10.5 2020-04-10 11:44:22

Usage:
  command [options] [arguments]

Options:
  -h, --help                     Display this help message
  -q, --quiet                    Do not output any message
  -V, --version                  Display this application version
      --ansi                     Force ANSI output
      --no-ansi                  Disable ANSI output
  -n, --no-interaction           Do not ask any interactive question
      --profile                  Display timing and memory usage information
      --no-plugins               Whether to disable plugins.
  -d, --working-dir=WORKING-DIR  If specified, use the given directory as working directory.
      --no-cache                 Prevent use of the cache
  -v|vv|vvv, --verbose           Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug
...

``` 



### Then install Nodejs & npm

[Source](https://ashokma.com/2019/02/18/install-nodejs-and-npm-pop-os/)

Start by updating the packages list by typing:


```
sudo apt update
``` 

### Install nodejs using the apt package manager:


```
sudo apt install nodejs npm
``` 

### To launch:


```
nodejs
``` 

### To verify:


```
node -v && npm -v 
``` 


### Then you can install the Tailwind boilerplate into your WordPress theme folder:

[Source](https://github.com/jeffreyvr/tailpress)

Open the themes folder in VS Code (where all your themes are NOT the exact theme order (in case it does not exist yet))

Open a terminal in VS Code


```
composer global require jeffreyvanrossum/tailpress-installer

``` 

Clone repo


```
git clone https://github.com/jeffreyvr/tailpress.git && cd tailpress
``` 

Run

```
rm -rf .git
``` 

Run


```
npm install
``` 

Run


```
npm run watch
``` 
to start developing

And now you can use Tailwind CSS Intellisense...

Hope it helps!

Comment if it is! :)

Good Luck!

***
If there is something wrong, don't hesitate to comment it under, so I can correct my article. Thanks!


