---
ID: 354
post_title: >
  Modernizr Fallback to jQuery UI for
  Native Datepickers
author: Josh
post_date: 2015-10-18 17:06:31
post_excerpt: |
  <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date">Native HTML 5 datepickers</a> are great, they offer a simple to use interface (that works particularly well on mobile) plus they're dead simple, just stick a <code>[type=date]</code> attribute on a <code>&lt;input&gt;</code> element and away you go. However, not all browsers support this so and will simply fall back to <code>[type=text]</code> so a fallback is required for <a href="http://caniuse.com/#feat=input-datetime">unsupported browsers</a>...
layout: post
permalink: >
  https://iamjoshellis.com/2015/10/18/modernizr-fallback-to-jquery-ui-for-native-datepickers/
published: true
subtitle:
  - ""
dsq_thread_id:
  - "4990689592"
dsq_needs_sync:
  - "1"
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
medium_post:
  - 'O:11:"Medium_Post":11:{s:16:"author_image_url";N;s:10:"author_url";N;s:11:"byline_name";N;s:12:"byline_email";N;s:10:"cross_link";s:3:"yes";s:2:"id";N;s:21:"follower_notification";s:3:"yes";s:7:"license";s:19:"all-rights-reserved";s:14:"publication_id";s:2:"-1";s:6:"status";s:4:"none";s:3:"url";N;}'
---
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date">Native HTML 5 datepickers</a> are great, they offer a simple to use interface (that works particularly well on mobile) plus they're dead simple, just stick a <code>[type=date]</code> attribute on a <code>&lt;input&gt;</code> element and away you go. However, not all browsers support this so and will simply fall back to <code>[type=text]</code> so a fallback is required for <a href="http://caniuse.com/#feat=input-datetime">unsupported browsers</a>...
<h2>Enter Modernizr</h2>
<a href="https://modernizr.com/">Modernizr</a> is a Javascript library that contains a collection of tests – or “detects” that tells you what HTML, CSS and JavaScript features the user’s browser has to offer. Feature dection using Modernizr looks something like this:
<pre><code class="language-javascript">if (Modernizr.awesomeNewFeature) {
  doSupportedStuff();
} else {
  doFallback();
}</code>
</pre>
<h2>Detecting Support for Native Datepickers</h2>
Applying this to our datepicker, we can detect support for <code>&lt;input type="date"&gt;</code> with a statement like this:
<pre><code class="language-javascript">if (Modernizr.inputtypes.date) {
  /* Yeah, datepickers all round! */
} else {
  /* Doh, no datepickers this time! */
}</code>
</pre>
<h2>Providing a Fallback</h2>
If the feature is unsupported we can apply the jQuery UI to any <code>&lt;input&gt;</code> elements with a <code>type="date"</code> attribute.
<pre><code class="language-javascript">if (!Modernizr.inputtypes.date) {
  /* apply datepicker ui to selected element */
  $('input[type=date]').datepicker({
    /* Keep the date consistent */
    dateFormat: 'yy-mm-dd'
  });
}</code>
</pre>
Note the reversal of logic here using the <code>!</code> operator, this just simplifies our code as we don't need to do anything if <em>does</em> support the date feature. The <code>dateFormat: 'yy-mm-dd'</code> just keeps the date format consistent between the jQuery UI datepicker and the native one.
<h2>Gettin' Fancy</h2>
The example above assumes that you'll have already pulled in the jQuery UI library and css, but if you're only using those for this particular fallback you could end up adding a lot of weight for users even if their browser <em>does</em> support the date feature. Well we can choose to only include those assets <em>if</em> the user needs them using Modernizr too!
<pre><code class="language-javascript">if (!Modernizr.inputtypes.date) {
    /* get jQuery-ui css */
    $('', {
      rel: 'stylesheet',
      type: 'text/css',
      href: 'https://code.jquery.com/ui/1.11.2/themes/smoothness/jquery-ui.css'
    }).appendTo('head');
    /* get jQuery-ui */
    jQuery.getScript('https://cdnjs.cloudflare.com/ajax/libs/jqueryui/1.11.2/jquery-ui.min.js')
    /* wait till it's loaded */
    .done(function() {
      /* apply datepicker ui to selected element */
      $('input[type=date]').datepicker({
      /* Keep the date consistent */
      dateFormat: 'yy-mm-dd'
    });
  });
}</code>
</pre>
The order here is important and the use of the <code>.done()</code> method, we need to make sure the assets are loaded before applying the the jQuery UI datepicker, or we're gonna have a bad time!
<p class="codepen" data-height="400" data-theme-id="17223" data-slug-hash="qOqKqg" data-default-tab="result" data-user="iamjoshellis">See the Pen <a href="http://codepen.io/iamjoshellis/pen/qOqKqg/">Input Date with Modernizr Fallback</a> by Josh (<a href="http://codepen.io/iamjoshellis">@iamjoshellis</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>