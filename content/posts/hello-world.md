---
title: "Hello World"
date: 2021-08-29T22:15:03+05:30
draft: false
---

Hello World!

I am planning to blogg my thoughts and learnings here. I have been writing in my head a lot these days! 
Today I finally decided to make it a reality. After all my tagline on facebook was "Coder. Dreamer. Developer" xD
Also, I would like this to be a place where I can come back when I need a refresher.

Today it is about: 
1. Creating a new hugo site for my blog
2. Hosting this on github pages using the domain ashwinimanoj.dev

If you are seeing this (and you are not me) then I succeeded! 

---

To start with, I thougth I could use ubuntu. Looking at hugo's documentation, I realised that brew is avaialble for linux! 
So I went ahead and installed brew. Using which I installed hugo. 

```https://docs.brew.sh/Homebrew-on-Linux```

And then it was about 

```
brew install hugo

hugo new site myblog

```

Now came the toughest part, choosing a theme! I went through the themes page and really liked Diary. Here's how to add it 

```
cd myblog
git submodule add https://github.com/AmazingRise/hugo-theme-diary.git themes/diary

```

Now that theme is done, I wanted to create a nice first post, hence this! 

```
hugo new posts/hello-world.md
```

