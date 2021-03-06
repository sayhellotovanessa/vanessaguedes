---
layout: post
title: "Installing Hugo"
date: 2017-05-01
categories:
- Tutorial
description:
image: /img/nathan-anderson-hugo.jpg
image-sm: /img/nathan-anderson-hugo.jpg
---

Today I played a little bit with a simple CMS written in Golang. Then I decided to share how to setup your own golang blog locally.
So here I have the steps I took to run my small blog in [Hugo](https://gohugo.io/).
The next article will be about how to pusblish Hugo on Heroku. Soon!

## Getting Hugo

I installed Hugo directly from the link source. I am using a Ubuntu 16.04 machine. You can choose the best Hugo release for you operational system [here](https://github.com/spf13/hugo/releases).

`$ wget https://github.com/spf13/hugo/releases/download/v0.20.6/hugo_0.20.6_Linux-64bit.deb
`

Check your version.

`$ hugo version`

I recommend anything higher than version 0.18.

![Folders list](/img/hugobg0.jpg)

## Creating a Hugo blog locally


Let's the fun begin! So you must create a new folder with your new blog name (in this case, Go Hugo).

`$ mkdir go-hugo`

`$ cd go-hugo`

Create the new blog:

`$ hugo new site .`

`$ la`

It must have 6 directories and 1 file.

![Folders list](/img/tree-0.jpg)

Then you need to create your first content.

`$ hugo new content/post/first-post.md`

(OR you can simply download [these files](https://github.com/spf13/hugo/tree/master/examples/blog/content/post) from Github and move them to your `/content` folder).

By what I read on the Hugo themes, all .md files in the content folder root are pages.

If you open this new `first-post.md` file in your code editor (Atom, Sublime, Vim or Gedit, etc) you can edit its metadata by adding this to the top of the file:

```
+++

title = "My first post"
date = "2017-01-01T14:11:55+09:00"

+++

Your content goes here (and you must use that old and nice markdown).
[Cheatset here] (https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet)
```

## Hugo customization and serve


Add a theme to your Hugo blog. I am taking the Beautiful Hugo theme as our example.

`$ git clone https://github.com/halogenica/beautifulhugo.git themes/beauty `

After this last step in your configuration, your blog is ready to be run.

`$ hugo server --theme=beauty`

Check your new blog on your browser by typing `http://localhost:1313`.

![Running new website](/img/hugo-run-0.png)
_(This image shows another Hugo theme I was testing before, so don`t be disapointed if you get a different Hugo appearance)._

Now you can start messing around your installation. You can build and deploy it in many free hosting services. I did it on Heroku and will write about it.
