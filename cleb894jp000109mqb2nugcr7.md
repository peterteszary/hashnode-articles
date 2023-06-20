---
title: "How To Set up a development environment for C# on Linux without Visual Studio?"
datePublished: Sun Feb 19 2023 10:09:49 GMT+0000 (Coordinated Universal Time)
cuid: cleb894jp000109mqb2nugcr7
slug: how-to-set-up-a-development-environment-for-c-on-linux-without-visual-studio
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1676800867601/2d8eebc6-9b8b-4853-acad-d25decf32a5d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1676801365706/d9e6508b-2f09-4076-ac48-4b1f72ca9706.jpeg
tags: csharp, linux, net, linux-for-beginners, linux-basics

---

## Why?

I am learning programming in an adult education system. So we learn several programming languages at the same time. We recently started working with C#. C# development requires a .net framework, which is basically made for the Windows platform.

That is why it is difficult to write and run such programs on Linux. However, it is not impossible. It is possible to develop in Visual Studio code but VS Code was not really designed for this. It can be used to solve the advantages of the C# development environment with different add-ons.

### Programming C# on Linux without Visual Studio or Visual Studio Code

With another method, however, we can create an environment (which has worked well for me so far). If you want a free environment that also runs under Linux, then using MonoDevelop IDE can be a good alternative.

[Monodevelop's website](https://www.monodevelop.com/)

I switched to Linux about two years ago, which I wrote about in this post. Since then I have avoided having to touch Windows again. This time is no different, but due to my studies, I have to make certain compromises. In any case, as long as it can be solved in another way, I am looking for solutions of this kind.

Note: Everything, that works with Ubuntu should work with Pop OS as well because Pop OS is based on Ubuntu.

### Installation

So, here's how to install MonoDevelop IDE on your Linux system (I'm using Pop OS).

Install MonoDevelop with these commands in your terminal:

```plaintext
sudo apt install apt-transport-https dirmngr sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF echo "deb https://download.mono-project.com/repo/ubuntu vs-bionic main" | sudo tee /etc/apt/sources.list.d/mono-official-vs.list sudo apt update
```

You might need to install .net framework:

**Step 1 – Enable Microsoft PPA**

In your terminal enter these:

```plaintext
wget <https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.debsudo> dpkg -i packages-microsoft-prod.deb
```

**Step 2 – Installing .NET Core SDK on Ubuntu**

```plaintext
sudo apt install apt-transport-https
sudo apt update
sudo apt install dotnet-sdk-6.0
```

**Step 3 – Installing .NET Core Runtime on Ubuntu**

```plaintext
sudo apt install apt-transport-https
sudo apt update
sudo apt install dotnet-runtime-6.0
```

**Step 4 – Check .NET Core Version**

```plaintext
dotnet --version
```

You can create your first program by creating a new solution:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676800458200/22fe694e-7f60-44c4-ae79-fa9977598283.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676800503409/7e4c0144-3004-49dd-aaa9-f81a9c8b4a8b.png align="center")

That is the code:

```plaintext
using System;

namespace HelloWorld
{
    class MainClass
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

It WORKS!!! :)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676800537242/8a935016-8d49-40da-8382-09e8d1cea43e.png align="center")

### Possible Error

**You might face this error running your first program:**

*"ApplicationName='/usr/lib/gnome-terminal/gnome-terminal-server', CommandLine='--app-id mono.develop.id0771a7bfd5a6445f82d97a8fe5fc4abc', CurrentDirectory='', Native error= Cannot find the specified file"*

I have solved it using this script on the terminal :

```plaintext
cd /usr/lib
sudo mkdir gnome-terminal
cd gnome-terminal
sudo ln -s /usr/libexec/gnome-terminal-server
```

So this is how I made C# work on my Pop OS Distro.

Hope it helps! :)