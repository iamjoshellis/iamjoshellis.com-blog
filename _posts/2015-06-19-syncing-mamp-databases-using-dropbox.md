---
ID: 306
post_title: Syncing MAMP Databases Using Dropbox
author: Josh
post_date: 2015-06-19 20:55:32
post_excerpt: "Like many people, when I first started working with Wordpress I used MAMP for my local development environment, but I also used multiple machines which can cause issues when I have different databases. Luckily it's pretty simple to sync MAMP databases via Dropbox."
layout: post
permalink: >
  https://iamjoshellis.com/2015/06/19/syncing-mamp-databases-using-dropbox/
published: true
subtitle:
  - ""
no_images:
  - "0"
cover:
  - "0"
banner_image_center:
  - ""
banner_image_left:
  - ""
banner_image_right:
  - ""
background_image:
  - ""
background_iframe:
  - ""
link:
  - ""
dsq_needs_sync:
  - "1"
---
Like many people, when I first started working with Wordpress I used MAMP for my local development environment, but I also used multiple machines which can cause issues when I have different databases. Luckily it's pretty simple to sync MAMP databases via Dropbox.

<h2>Move the databases to Dropbox</h2>

First of all move your databases from:

<pre class="language-bash"><code>/Applications/MAMP/db</code></pre>

To somewhere in Dropbox, for example:

<pre class="language-bash"><code>~/Dropbox/Apps/MAMP/db</code></pre>

<h2>Create a symlink</h2>

Now add a <a href="http://iamjoshellis.com/blog/os-x-symbolic-links/">symlink</a> from MAMP to Dropbox:

<pre class="language-bash"><code>ln -s </code><code>~/Dropbox/Apps/MAMP/db </code><code>/Applications/MAMP/db</code></pre>

Thats's it!

<div class="box-danger"><strong>Disclaimer: This could cause issues if you run MAMP on multiple sync'd machines at the same time... so don't.</strong></div>