---
ID: 321
post_title: >
  How to Run Multiple Local WordPress
  Sites using MAMP on OS X
author: Josh
post_date: 2015-06-30 22:31:42
post_excerpt: ""
layout: post
permalink: >
  https://iamjoshellis.com/2015/06/30/how-to-run-multiple-local-wordpress-sites-using-mamp-on-os-x/
published: true
subtitle:
  - ""
dsq_needs_sync:
  - "1"
---
<a href="https://www.mamp.info/en/">MAMP</a> is a simple to use tool and is often a staple in a Wordpress developer's tools. When you start, you only have a single "domain" <code>http://localhost/</code> making working on multiple local sites a bit of a problem. Additional sites can be added by adding <em>virtual hosts</em>, this can seem a bit daunting if you've never done it before, but is actually quite simple.
<h2>The Hosts File</h2>
A <em>hosts</em> file can be used to point requests for a domain to an IP address, by creating a <em>virtual host </em>it can tell our device our domain is hosted locally,<strong> not </strong>online.

To edit the hosts file, open up Terminal and type the following:
<pre><code class="language-bash">sudo nano /etc/hosts</code></pre>
<code>sudo</code> simply means to execute the command as <em>root</em>, <code>nano</code> is the text editor we'll be using and <code>/etc/hosts/</code> is the location of the <em>hosts</em> file. You'll be prompted for your OS X password (a administrative password is required when using <code>root</code>.)

You'll then be presented with a file where the bottom few lines look something like this:
<pre><code class="language-bash">127.0.0.1       localhost
255.255.255.255 broadcasthost
::1             localhost
</code></pre>
<code>127.0.0.1</code> is 127.0.0.1 is an IP address that refers back to the local device, it's how a computer refers to itself.
<strong>Disclaimer: Don't remove any existing entries to your hosts file, bad things will happen!</strong>

To add your local domain simply enter <code>127.0.0.1</code> followed by your domain, for example:
<pre><code class="language-bash">127.0.0.1       myawesomesite.dev</code></pre>
<strong>Tip: Avoid domain names with <code>.local</code> on the end as this can cause issues with Bonjour.</strong>

When you're done press Ctrl-O, enter, then Ctrl-X followed by enter again (this saves the file and closes the editor.)
<h2>The Apache Config File</h2>
We've successfully told our device that our domain is local, but we still need to point our web server (Apache, it's the <em>A</em> in <em>MAMP</em>) at the right <em>directory</em> (where the files are stored) for our site.

To do so, we need to edit our Apache config file stored here:
<pre><code class="language-bash">/Applications/MAMP/conf/apache</code></pre>
Open it with any text editor, scroll all the way to the bottom and add the following:
<pre><code class="language-bash">&lt;VirtualHost *&gt;
DocumentRoot "<em>directory</em>"
ServerName <em>domain</em>
&lt;/VirtualHost&gt;
</code></pre>
Replacing <code><em>directory</em></code> with the path to the file for the site and <code><em>domain</em></code> with the domain we added to <em>hosts</em> earlier, for example:
<pre><code class="language-bash">&lt;VirtualHost *&gt;
DocumentRoot "/users/josh/sites/myawesomesite"
ServerName <em>myawesomesite.dev</em>
&lt;/VirtualHost&gt;
</code></pre>
Save the file and you're done! Start up MAMP and enter your domain in your browser. You can simply rinse and repeat these steps to add as more sites...