---
title: "#Day1 - What will this series be about?"
datePublished: Mon Feb 19 2024 12:59:36 GMT+0000 (Coordinated Universal Time)
cuid: clssy1e2u000009l47tcvdwcu
slug: day1-what-will-this-series-be-about
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ZR48YvUpk04/upload/22042aaf7c04473644af8ac2a44c92ed.jpeg
tags: developer, diary

---

## Introduction

Well, this developer series will actually be the developer diary for my project task, which I have to finish by April.

During the project, I'll be creating a Desktop application that will help users to simplify the process of uploading products to a WordPress/WooCommerce webshop.

It will consist of 3 components / 3 programs. The first is a C# desktop application. It is C# because the task was to be done in it. I wanted it in Java, but the choice was nominal. In reality, C# was mandatory.

I have previous diary entries which I will paste here at the end of the post, just so that everything is actually included here.

Development is complicated by the fact that I basically develop under Linux, and the C# application has to include elements that can only be developed in a Windows environment.

Also, an additional difficulty is that the code has to be uploaded to a separate Github repository, so a separate user/email address is required.

I will write more about the other difficulties and the strange experiences I had. In any case, this is the introduction for now.

The goal is to be able to devote 2 hours every day to the project (minimum) and to keep a developer log here, which I will upload to the development repo later. This way I can keep up with the progress in parallel and keep track of the development.

## Previous posts:

### 2023-10-09

After many attempts I could not install the node packages that are specified in the package.json file. I tried on Windows and I tried in linux environment. I think the problem is that the package.json was updated in the meantime and it can't find the dependencies anymore. So I will try again tomorrow, but with a different method. I just wrote this down so that I don't forget where I was.

### 2023-10-11

Yesterday I tried to put up the node packages by putting a Xampp on my linux operating system and creating a WordPress environment there. This made the nmp install work, although it turned out that I had installed a package included in a 2019 package.json file that was a bit outdated. So I modified the package.json file. The update was then successful.

Today I tried to create the same environment with an application called DevKinsta. The problem with Windows was that due to Docker virtualization, a virtual path was given to the node package when installing it, so it didn't find the "not real" i.e. virtual location. Therefore it could not install the node modules. However, on linux, the modules were installed without a bone.

That's why I included the node modules in a .gitignore header, so that they would not be committed to the repository unnecessarily.

**2023-11-11**

Today I worked on creating the documentation page of the package with Vuepress. The page is functional, but only locally for now. For some reason the client compile fails on deploy. I couldn't figure out what was wrong. Anyway, Vuepress is a bit fragile. I ran it 4-5 times before I managed to get a stable version of V.1. Of course I tried the newer versions, but they were even less stable. I also added new tasks to Jira. Writing code and designing interfaces.

Here:

Describing operational processes verbally, then algorithmically as branch diagrams. Then design the different screenshots for these steps.

First, from big to small. So first the global operation, then the smaller processes broken down into units.

My further plan for today and tomorrow is to implement these and progress with the development of the WordPress theme. At the same time I would like to start developing the plugin.

It will also be worth writing down now which tables from the WordPress database will be needed for the desktop application.

### 2024-02-05-11

This week, I created the exam rooms desktop application from scratch. Deconstructing the previous Chalk application would have been a cumbersome, time-consuming and error-prone option. I therefore decided to create it from scratch.

Currently I have the following pages (front end):

* Login
    
* Add Product
    
* Search Product
    
* Welcome Page
    

I have also started to add the colours to make the final state as similar as possible to the design plan.

I also started developing the plugin. But since the Sparse Checkout still doesn't work properly, I started to add the commits under our own Organization. I will copy this into the exam repository. So I'm going to work doubly hard, which is why I can't figure out how to make sparse checkout work properly. For now, I didn't want to waste any more time with it.

### 2024-02-12

Today I plan to move my previous logs from the Confluence interface here. Also, I would like to create the documentation page in VitePress. I also want to implement the sorting of the repositories.

Other plans for today include uploading tasks for development and coming up with deadlines.

Since I've done everything in the project so far, I'd also like to organize everything in the project so far on my own.

### 2024-02-13

Today I cleaned up the repositories. That means I deleted all the folders that we don't need. Peter Bagi asked his tutor that the initial folder structure is just a template, so we can modify it as needed. I did so.

I also created the projects, milestones and tasks for the repository. 3 projects to be exact. Separately, for each of our programs.

Here I also modified the different elements for the project, like the "difficulty" of the tasks and the naming of the task type.

I also deleted unnecessary Repos in the Team's own organization. I'm still working on this organization because I'll commit WordPress-related improvements here first, due to the "peculiarities" of WordPress. These are explained in the related section of the documentation.