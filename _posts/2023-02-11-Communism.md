---
layout: posts
title:  "Communism ZSH Plugin"
date:   2023-02-11 02:03:50 -0700
tags: Projects
---

One of the earliest projects I did as I was learning Unix, starting with ZSH on my Macbook. I wrote a little plugin for oh-my-zsh that pulls a Marx quote with each new terminal session and adds some beautiful red imagery to your terminal. 

In the future I want to add more quotes and probably have configuration options for a much smaller hammer & sickle - more to come :)

<img width="909" alt="Screen Shot 2022-09-28 at 4 01 15 AM" src="https://user-images.githubusercontent.com/9009959/192763072-f36792ee-f028-4ade-917c-46e64d67f966.png">

[A chill startup plugin](https://github.com/victoria-riley-barnett/Communism)

Requires oh-my-zsh

Place in /Users/user/.oh-my-zsh/custom/plugins, in a parent folder named "anything" (I used 'communism'). Then, cd back to root and edit .zshrc to include your plugin. 

plugins=(... communism)
