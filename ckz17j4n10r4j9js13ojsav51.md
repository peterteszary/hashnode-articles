---
title: "WordPress BoilerPlate Chase"
datePublished: Sun Jan 30 2022 11:56:19 GMT+0000 (Coordinated Universal Time)
cuid: ckz17j4n10r4j9js13ojsav51
slug: wordpress-boilerplate-chase
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643544001511/7uMeybYj6.jpeg
tags: wordpress-themes, linux, wordpress, nodejs, developer

---

At the beginning of this year, I wanted to gain my skills in custom theme development, but I wanted to do it the proper way. So, I started to look around some boilerplates, to see what is inside them, how they build up, and what kind of plus they can give while developing my "test" theme. 

> 
A WordPress theme boilerplate is a WordPress starter pack, that has different modules in it, like Node.js/npm, Bootsrap, Gulp, SCSS, etc., and also has the core template files that a template has to have to start building from scratch. But it does not have layouts and such, so you have to build everything yourself. It is really a starter pack, to build custom themes.

I've seen a lot of Youtube videos and I have a couple of paid Udemy courses, but as time goes on I notice that there is no simple solution. I've started from scratch via a Udemy course, but later on, I realized, that there are much more options, and even the rhythm of the course is too slow. So, I've jumped right into the Youtube maze of WP dev videos. I've found a good one, but then I saw that I have to buy the development theme if I want to follow along. I've seen another one, but then I saw that there were no node modules in it (I've wanted to learn that part too, that is why it is important).

OK.

Then I started to look around because there are lots of free boilerplates out there. 
 I have found  [https://roots.io/](Link) . Man, that stuff looks amazing. It has all that stuff. Node.js, npm, composer, Bootsrap, Tailwind, Bulma, scss, and all that. Superb! I've started to check it out right after. But I had some trouble by trying to breathe life into it. I've been trying for days to get it to work. No luck. So after tons of searches on different sites, like the classic StackOverflow, I've decided to ask some questions in the Roots Sage Github Repo. 

> 
Problem 1
- illuminate/support is locked to version v5.6.39 and an update of this package was not requested.
- illuminate/support v5.6.39 requires ext-mbstring * -> it is missing from your system. Install or enable PHP's mbstring extension.
Problem 2
- squizlabs/php_codesniffer is locked to version 2.9.2 and an update of this package was not requested.
- squizlabs/php_codesniffer 2.9.2 requires ext-simplexml * -> it is missing from your system. Install or enable PHP's simplexml extension.
Problem 3
- illuminate/support v5.6.39 requires ext-mbstring * -> it is missing from your system. Install or enable PHP's mbstring extension.
- illuminate/console v5.6.39 requires illuminate/support 5.6.* -> satisfiable by illuminate/support[v5.6.39].
- illuminate/console is locked to version v5.6.39 and an update of this package was not requested.

I've reported it as a bug, and also give all the information to them, to even reproduce the circumstances. But after a day, they replied, that I should do as I have found in an article (that I also added to my report) because there are some PHP packages and other dependencies that are missing. And then they there way another short answer with similar advice and then they closed my bug report.  

After that, I have contacted one of my friends who is proficient in DevOps and System Administration things. After a long investigation, we found out that there is some compatibility issue with Pop OS (21.10) (It was a fresh 1-day install). Even it is based on Ubuntu it has some problems with the PHP extensions. We have solved the Node problem, but we could not find a solution for the PHP extension problem. We have tried everything and it did not work. 

My article about why I've switched to POP OS is  [>HERE<](/why-pop-os-is-my-favorite-linux-distro) 

I've commented under my closed bug report, maybe someone might need it in the future. Even the support could not give me the solution, I don't want others to hang on to this problem without having some answer or without any compass for days. 

The reason we came to the conclusion that Pop OS is the problem is that we have installed Docker, and it worked perfectly in a Docker image. By the way, even if it is an OS compatibility issue, why does it have to be "rocket science" to install a boilerplate? Why should you investigate for days (and nights) just to find out that there is an OS compatibility issue? So Sage is a super boilerplate, but I will just let it go. I will find some easier boilerplate for my study purposes. But this will be another story.
