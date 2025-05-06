---
title: Launch MCP Client on Termux
author: jaeman
date: 2025-03-31 16:41:00 +0900
categories: [Termux]
tags: [Termux, Debian, GUI, Android, VSCode]
toc: true
---

## Prerequisition
- Linux GUI Installed(Debian or Ubuntu)
- Browser Installed(recommend Firefox)
- VSCode Installed(see my [previous post](https://jaemani.github.io/posts/Termux-Setup-VSCode/))

## Claude Desktop on debian arm64
...(Skip for the detail)  
I tried to install Claude Desktop via Wine86 & Wine64 which supports:  
*translates Windows API calls into POSIX calls on-the-fly, eliminating the performance and memory penalties of other methods and allowing you to cleanly integrate Windows applications into your desktop. - WineHQ*  
  
So I really expexted that Claude Desktop would be also installed in arm64 Termux powered environment, like I already have successfully installed and launched the Undertale - Windows Version Game.  
  
But it always occured the error and crashes while the installer is running.  
![1743406866337-2](https://github.com/user-attachments/assets/86adef86-110b-4f5d-bb25-86e793d8bb7f)
![1743406866337-1](https://github.com/user-attachments/assets/2bfc4dc9-6b12-4314-b0b3-02dae09ee12b)  *Unlike The Undertale was launched perfectly, Claude Desktop Installer couldn't :(*  
  
Maybe one day it would be launched, when proot debian/wine find the new ways to solve it or Claude Desktop release the portable version of App. But it's just not today.

> You Can Launch Apps through GPU Accaleration to improve clicking and dragging GUI response
{: .prompt-tip }

## Alternatives - [Cline](https://cline.bot/)
To Achive the goal of Launch MCP on Tablet, I had to find alternatives to replace Claude Desktop.  
I have saw several MCP Clients in the Github Repo [Awesome MCP Clients](https://github.com/punkpeye/awesome-mcp-clients).  
   
![image](https://github.com/user-attachments/assets/cbdfd204-40e9-42d2-9378-46d7c44048eb)  
<img width="486" alt="Screenshot16 18 12" src="https://github.com/user-attachments/assets/5a4dac54-38ab-4529-8023-0c769670584a" />  *Cline info - Awsome MCP Clients page*  
  
When I found out the **Cline** is the VSCode extension, I decided to try this guy first. Since I had already installed VSCode and it was very stable enough to I can do my Coding Assignment on my tablet.
  
It was super easy.  
All I have to do was just install the **cline extension** in VSCode Marketplace.  

And then follow the guide of cline provides.  
There are also very good materials at Cline Official [Blog](https://cline.bot/blog) and [Docs](https://docs.cline.bot/)
- [Context Management](https://docs.cline.bot/getting-started/understanding-context-management)
- [Model Selection Guide](https://docs.cline.bot/getting-started/model-selection-guide)
  
It is very impressive the MCP Client runs on my panel of VSCode!  
<video width='620' autoplay type="video/mp4" src="https://cline.ghost.io/content/media/2025/03/cline-investigating-cline-1.mp4" />  
  
This post is only about the guide to install MCP Client, so I would not handle about environment setting and project building guide here.  
I'll post later about MCP itself later. Enjoy your MCP Coding!
