---
title: "#Day7 - Moving forward with the Desktop Application"
datePublished: Wed Mar 13 2024 15:47:22 GMT+0000 (Coordinated Universal Time)
cuid: cltpz5qyc000809l8fw4pcnpb
slug: day7-moving-forward-with-the-desktop-application
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/NqOInJ-ttqM/upload/007c272393fae3646ba318b022c97647.jpeg
tags: csharp, design

---

Today, I made some changes to the Desktop application. I created a NewProductWindow instead of AddProductView. This creates a popup window when adding a product, instead of navigating to anywhere. Alternatively, in the Search ProductView, I have also created an EditProductWindow that pops up when you click on the "Modify" button and then you can use it to modify the product. So again, no need to navigate away from the list of products, but it makes it easier to use.

When you save, of course, it also saves the modifications. SQLite is a perfect choice for the interim. I would like to write the backend for it later for the API connection and linking, but for now, it serves what is needed perfectly.

While I test the NewProduct feature, I have created an extra menu item. I'm not even deleting the previous Add Product menu item until this is working.

Also, I would like to add a title bar to each page or window so the user knows where they are.

One extra thing that I'll have to work out is to have tiny checkboxes next to the products in the SearchProductView, which will act as radio buttons. These are needed to allow the user to select which product they want to edit. That is, he can only select the product he wants to edit. I do not want to complicate the program with group editing for the moment. I would rather have it work in a stable way. But I'm almost at the finish.