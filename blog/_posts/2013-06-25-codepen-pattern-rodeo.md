---
layout: blog_post_code
title: Codepen Pattern Rodeo
excerpt: It always amazes me what people come up with &amp; create on Codepen. I’ve been meaning to make a pen for a while but have always put it off. After keeping my eye on the weekly <a href="http://blog.codepen.io/rodeo/season-two/#week-four" target="_blank">Pattern Rodeo challenge</a>, I decided that it would be a good excuse to a make a pen and learn a new skill.
---
<p class="intro">It always amazes me what people come up with &amp; create on Codepen. I’ve been meaning to make a pen for a while but have always put it off. After keeping my eye on the weekly <a href="http://blog.codepen.io/rodeo/season-two/#week-four" target="_blank">Pattern Rodeo challenge</a>, I decided that it would be a good excuse to a make a pen and learn a new skill.</p>

<h3 class="heading">The challenge</h3>
<p>Start with a <a href="http://codepen.io/chriscoyier/pen/luIkw" target="_blank">form</a> on this Pen (a customized version of a Wufoo form) and go nuts, making it as beautiful and useable as you can. You can change the HTML, CSS, and add JavaScript as you please, just make sure the questions and choices are just as they are in the original form.</p>

<h3 class="heading">Idea</h3>
<p>Break the form into sections having each panel fold in when the user clicks next, using CSS transforms and CSS transitions to create the effect. This would require having all the panels sit at 90 degrees so you can’t see them, then make them sit at 0 degrees.</p>

<p>The first thing I did was add a class called 'disabled' to all the sections, exluding the first one. When the user clicks next section I removed the 'disabled' class on the very next section and replaced it with a class called 'enabled'. At the basic’s it was set up like this:</p>

<?prettify?>
<pre class="prettyprint lang-css">
<xmp>
li {
    transition:all 1s ease-in-out;
}

.disabled{
    display: none;
    -webkit-transform:rotateX(90deg);
    -moz-transform:rotateX(90deg);
    -o-transform:rotateX(90deg);
    transform:rotateX(90deg);
}

.enabled {
    display: block;
    -webkit-transform:rotateX(0deg);
    -moz-transform:rotateX(0deg);
    -o-transform:rotateX(0deg);
    transform:rotateX(0deg);
}
</xmp>
</pre>

<h3 class="heading">Issue</h3>
<p>The sections would appear but the transition would not work.</p>

<h3 class="heading">Solution</h3>
<p>After some research I found out that CSS transitions do not support the display property. Using a different method of hiding the sections worked. Giving the sections height: 0 and visibility: hidden made sure it was invisible.</p>

<?prettify?>
<pre class="prettyprint lang-css">
<xmp>
.disabled{
    visibility: hidden;
    height: 0;
    -webkit-transform:rotateX(90deg);
    -moz-transform:rotateX(90deg);
    -o-transform:rotateX(90deg);
    transform:rotateX(90deg);
}

.enabled {
    padding: emCalc(30px);
    height: auto;
    -webkit-transform:rotateX(0deg);
    -moz-transform:rotateX(0deg);
    -o-transform:rotateX(0deg);
    transform:rotateX(0deg);
}
</xmp>
</pre>

<h3 class="heading">Success</h3>
<p>Throughout the week, users vote on their favourite pen’s, the winner receiving a free PRO account for a year, plus a free CodePen swag bag, including a T-Shirt, pen (literally), and stickers. And runner ups winning a swag bag.</p>

<p>After the week was up my pen took out first place closely followed by a 3 way tie by some other excellent pens. </p>

<ul>
	<li>Winner: <a href="http://codepen.io/allanpope/pen/uxIeG" target="_blank">Allan Pope</a></li>
	<li>Runner up: <a href="http://codepen.io/awesomephant/pen/ucvkK" target="_blank">awesomephant</a>, <a href="http://codepen.io/pankajparashar/pen/xbAyl" target="_blank">Pankaj Parashar</a>, <a href="http://codepen.io/tjacobdesign/pen/aIGsn" target="_blank">Timothy Miller</a></li>
</ul>

<pre class="codepen" data-height="500" data-type="result" data-href="uxIeG" data-user="allanpope" data-safe="true"> <code> </code> </pre>
<script src="http://codepen.io/assets/embed/ei.js"> </script>