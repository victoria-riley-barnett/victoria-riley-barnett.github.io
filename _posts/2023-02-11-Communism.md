---
layout: posts
title:  "Communism ZSH Plugin"
date:   2023-02-11 02:03:50 -0700
tags: Projects
---

One of the earliest projects I did as I was learning Unix, starting with ZSH on my Macbook. I wrote a little plugin for oh-my-zsh that pulls a Marx quote with each new terminal session and adds some beautiful red imagery to your terminal. 

In the future I want to add more quotes and probably have configuration options for a much smaller hammer & sickle - more to come :)

<img width="900" alt="Screenshot of the app in my terminal on Arch" src="https://user-images.githubusercontent.com/9009959/218278604-390b7d68-1bba-425f-880b-4c40455559ce.png">

A chill ZSH startup plugin that adds Marx quotes and some wonderful red imagery to your terminal.

### Requires 
- oh-my-zsh

### Installation
```
cd ~/{wherever you put your OMZ plugins or scripts}
git clone --depth-1 https://github.com/victoria-riley-barnett/Communism
```
```
#Edit .zshrc to include your plugin. 
plugins=(... communism)
```
