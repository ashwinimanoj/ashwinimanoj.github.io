---
title: "Hello World"
date: 2021-08-29T22:15:03+05:30
draft: false
tags: ['hugo', 'getting-started']
---

# Hello, World! 🌍  

For the longest time, I’ve been writing thoughts and ideas in my head, waiting for the perfect moment to capture them somewhere concrete. Well, today’s the day! After much procrastination, I’ve decided to bring this blog to life. (Better late than never!)  

Since my Facebook tagline was **"Coder. Dreamer. Developer"**—it only feels right to document my tech adventures here! 😄  

More than just a space to share my musings, I want this blog to serve as a personal reference—something I can revisit whenever I need a refresher.  

## Today’s Agenda  

Here’s what I tackled today:  

1. **Setting up a new Hugo site**  
2. **Deploying it on GitHub Pages** using my domain: **ashwini.dev**  

If you’re reading this (and you aren’t me)... **I DID IT!** 🎉  

## Setting Up Hugo on Ubuntu 

I thought, “Why not use Ubuntu for this?” 🤔 And while following Hugo’s documentation, I found out that **Homebrew** works on Linux too! Game changer!  

### Steps to Set It Up  

1. **Install Homebrew**  
   Follow the instructions in the [Homebrew on Linux Documentation](https://docs.brew.sh/Homebrew-on-Linux).  

2. **Install Hugo** using Homebrew:  
   ```bash
   brew install hugo
   ```

3. **Create a New Hugo Site**:  
   ```bash
   hugo new site myblog
   ```

## Choosing a Theme  

This was the hardest part! There are so many amazing Hugo themes to choose from, but I eventually went with **Diary** because it resonated with me.  

Here’s how I added it to my project:  

```bash
cd myblog
git submodule add https://github.com/AmazingRise/hugo-theme-diary.git themes/diary
```

## Writing My First Post

Of course, I had to mark this moment with a proper “Hello World!” post.  

Here’s how I did it:  

```bash
hugo new posts/hello-world.md
```

---

## What’s Next? 

I’m excited to see where this blogging journey takes me. I’ll be sharing my learnings, challenges, and moments of joy along the way.  

If you made it this far, thanks for reading—you're awesome!  

Until next time, **happy coding!** 💻
