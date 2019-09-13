---
title: Welcome Back
date: 2018-10-10 14:35:58
tags: general
---

Let's count our failures up to times before this blog.
There were:

- Wordpress
- Blogspot
- Tumblr
- Blogspot (Again)
- Jekyll

Nothing wrong with them. They are good blogging platform.

The only one to blame is We.

Everytime we want to write a post. We had to start over from almost the very start.

Learning everything needed to just publish one post.
Thats how we fall and fail everytime.

\* Now we are going to use `Hexo!`

We choose `Cactus\light2` theme.

It looks simple but very nice.

We hope we feel at home with them.

Now, to help us starting-over writing again if anytime in the future somehow we've stopped blogging for whatever reason, let's prepare a quick note
stating exactly steps on how to get our feet wet once more time in this kind of mind-dumping world.

So let's follow these easy steps below!

1. Get things ready
2. Write a post
3. Publish

## 1. Get Things Ready

### the tools

we need locally:

- node
- npm
- hexo-cli
- markdown editor

### data persistance

after having those tools,

clone the blog from its repository.

here is the repository address:
> https://github.com/fitsyu/blog.git


there are two branches:

1. branch `write`

	This is similar to `develop` branch in a development project. Here we do all the work of writing and the blog internal system configuration

2. branch `master`

	This is the deploy target branch where command `hexo deploy` will generate static assets for public to consume.


## 2. Writing a Post

### Prepare the post
first, get into blog directory.

then execute `hexo new post <PostTitle>`

it should generate empty post file in source/_post

### Write
then edit the file to start writing by a command like this

`macdown source/_post/PostTitle.md`

### After Writing
when writing is done do these

snapshot the changes

`git add .`

`git commit -m "write new post"`

### Preview
to see the just-finised post we can do it with

`hexo server`

to launch local server serving the blog locally


## 3. Publish
after writing a post if we want it be seen by public

### prepare

first, generate the static files

`hexo generate`

### deploy

we can publish it this way

`hexo deploy`

open the site in a browser

hopefully it has sit there nicely along with others previous posts.

Thats it!.

We hope we write more as we develop, work, learn more.

To have nice contents is great.

But it would be even greate if we release it to world.

> Go write!
