---
ID: 335
post_title: >
  Using jQuery to Show/Hide Element Based
  on Dropdown Selection
author: Josh
post_date: 2015-07-24 20:31:23
post_excerpt: 'Just a quick code snippet to show how to show/hide html elements based on the active <code>option</code> in a <code>select</code> dropdown.'
layout: post
permalink: >
  https://iamjoshellis.com/2015/07/24/using-jquery-to-showhide-element-based-on-dropdown-selection-for-stats-nerds/
published: true
subtitle:
  - |
    Or "How to Avoid Writing any CSS if You're a Stats Nerd"
dsq_thread_id:
  - "4990700640"
dsq_needs_sync:
  - "1"
---
Just a quick code snippet to show how to show/hide html elements based on the active <code>option</code> in a <code>select</code> dropdown. It would be less jankey to apply a <code>.hidden</code> class with <code>display:none</code> and then change the class using jQuery. However a friend wanted to do this with just jQuery in RStudio (R is a programming language statisticians use, those nerds don't like css) this was what I suggested.
<p class="codepen" data-height="389" data-theme-id="17223" data-slug-hash="ZGqLYw" data-default-tab="result" data-user="iamjoshellis">See the Pen <a href="http://codepen.io/iamjoshellis/pen/ZGqLYw/">Show/Hide Element Based on Select, jQuery Only</a> by Josh (<a href="http://codepen.io/iamjoshellis">@iamjoshellis</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>