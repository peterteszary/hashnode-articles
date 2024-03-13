---
title: "#Day6 - Connections"
datePublished: Wed Mar 13 2024 15:36:28 GMT+0000 (Coordinated Universal Time)
cuid: cltpyrqdj000509i9e1jdfvo6
slug: day6-connections
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/8bghKxNU1j0/upload/013786ef19fe738834320a0e63f535c1.jpeg
tags: csharp, developer, connections

---

Today I will restructure the site and link the elements. What I don't understand is that I started using UserControls instead of Pages, because I was told that they eliminate the navigation arrows in the top left corner. However, they still appear, so now I am trying to move the various Views to Window bases. This might be useful later, by the way, because there are plans to not have a window switch when editing a product, but to be able to edit products conveniently in a pop-up window.

So today I have inserted the GlobalMenu into the MainWindow. I deleted the MainView because I didn't see the point. The same happened with the WelcomePageView, because it was unnecessary to have a separate page for it. From now on I will try to make the program as streamlined, better structured and free of unnecessary elements as possible.

Another problem is that I cannot display the logo. I have tried all kinds of paths in vain.

**So the problems:**

The logo does not appear. Pages have to be moved from UserControl to Window, because the navigation arrows still appear --&gt; These have become Pages because it didn't work with Window...

**Update.**

I managed to insert the logo. It works now. The simple method was to link it in the design interface by clicking on the item and then selecting the path. That way it worked.

Navigation between pages works too. I was also able to connect the database, so it is already stored in the database when the product is uploaded. The problem is that it overwrites the previous product for now. But I can see a solution.

Also, I prefer to include the whole Search Product window in the home page, since there is nothing there anyway. And the AddProduct will then appear as a popup window, so I can add the database lock function to the "Add Product" button. So it will break the database connection every time.

I also changed the colors, borders and layout in the Design. The program is finally starting to take shape.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710344104007/7857f46a-3750-4a20-9d53-2b41f4d67148.png align="left")

Tomorrow I would like to display the captured products in the Search Product window. And then I think I can start developing the extension.