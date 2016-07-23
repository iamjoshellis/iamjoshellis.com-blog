---
ID: 546
post_title: >
  How to Install a Specfic Version of
  Ansible
author: Josh
post_date: 2016-07-23 13:30:18
post_excerpt: |
  I'm a huge fan of the roots.io toolset for building and deploying high-quality WordPress sites. Part of that toolset is <a href="https://github.com/roots/trellis">Trellis</a> - a provisioning and deployment automation tool which typically requires a specific version of <a href="https://www.ansible.com/">Ansible</a>.
layout: post
permalink: >
  https://iamjoshellis.com/2016/07/23/install-specfic-version-ansible/
published: true
medium_post:
  - 'O:11:"Medium_Post":11:{s:16:"author_image_url";N;s:10:"author_url";N;s:11:"byline_name";N;s:12:"byline_email";N;s:10:"cross_link";s:3:"yes";s:2:"id";N;s:21:"follower_notification";s:3:"yes";s:7:"license";s:19:"all-rights-reserved";s:14:"publication_id";s:2:"-1";s:6:"status";s:4:"none";s:3:"url";N;}'
subtitle:
  - (Or any pip package)
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
---
I'm a huge fan of the roots.io toolset for building and deploying high-quality WordPress sites. Part of that toolset is <a href="https://github.com/roots/trellis">Trellis</a> - a provisioning and deployment automation tool which typically requires a specific version of <a href="https://www.ansible.com/">Ansible</a>.

You can install a specific version of Ansible via <a href="https://pip.pypa.io/en/stable/">Pip</a> with the following command:
<pre class="language-bash"><code>pip install ansible==2.0.2.0</code></pre>
Just replace <code>2.0.2.0</code> with the version you require.
<div class="box-alert">Note: Since this <em>globally</em> installs Ansible, you'll probably need to run the command as <em>root</em> using <code>sudo</code>.</div>