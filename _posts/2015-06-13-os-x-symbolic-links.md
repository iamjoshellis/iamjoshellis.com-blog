---
ID: 303
post_title: OS X Symbolic Links
author: Josh
post_date: 2015-06-13 18:09:06
post_excerpt: >
  Symbolic Links (or symlinks) simply
  contain the path of the target file or
  directory stored as text. This can be
  incredibly handy when trying to sync
  apps or data other multiple devices or
  drives.
layout: post
permalink: >
  https://iamjoshellis.com/2015/06/13/os-x-symbolic-links/
published: true
subtitle:
  - ""
dsq_thread_id:
  - "4987326092"
dsq_needs_sync:
  - "1"
---
Symbolic Links (or symlinks) simply contain the path of the target file or directory stored as text. This can be incredibly handy when trying to sync apps or data other multiple devices or drives. 

If you move the target file, the symlink will break because it still points to the original location. However, symlinks work in such a way that almost all applications and OS features will follow them to the target. 

Symlinks look like this...
<pre><code class="language-bash">ln -s target link</code></pre>
Where <code>target</code> is the path of the target file or folder and <code>link</code> is where the link will be created.