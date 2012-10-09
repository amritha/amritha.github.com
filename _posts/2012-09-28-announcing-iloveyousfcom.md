---
layout: post
title: "Announcing ILoveYouSF.com"

---

<div class="lemphasis">
<b> Meet ILoveYouSF.com </b>
</div>

<p>I am extremely proud to announce the launch of the hackathon project that <a href="http://www.twitter.com/sabrina">Sabrina</a> and I kicked off about a month ago. <a href="http://iloveyousf.com">ILoveYouSF</a> is very dear to my heart because not only has the site itself shaped up to be great, but I have learned so much along the way. Not to mention, it's been a blast building it. </p>

<div class="lemphasis">
<b> The Birth of a Hackathon </b>
</div>

<p>Have you ever wanted to ship something so badly that it hurts? Do you ever have crazy ideas in your head that you never quite have the time to pursue? Or what if you just don't have the tecnical skills needed to pursue them? These were the questions that Sabrina and I were tossing around when we decided that we wanted to buckle down and build something. </p>

<p>Given our social tendencies and inability to sit in one place for very long, we realized we'd have to take an extreme approach if we wanted to get anything done. Before we knew it, a bizarre forest lodge in Los Altos was booked via Airbnb, and we had blocked off our entire Labor Day weekend. In the days before, I was brushing up on Michael Hartl's comprehensive <a href="http://ruby.railstutorial.org/ruby-on-rails-tutorial-book">Rails tutorial</a>, and Sabrina was learning all kinds of amazing responsive web design techniques. I could and should write a blog post outlining the programming lessons learned throughout this process, but today I will focus on our product process. </p>

<div class="lemphasis">
<b>Scoping</b>
</div>

<p>So what were we going to build? No idea. Our dreams were set sky high, but they quickly came crashing down when we realized we had to scope a project that could actually be implemented in one weekend by two novices. Later on, we learned for ourselves the golden lesson: </p>

<em>Always double (or triple or quadruple) your scoping estimates. Chances are, nothing EVER gets done in the time that you expect. EVER.</em>

<p>Anyway. After loads of ideation and giggling, we decided on an idea that was sparked from an old Social Proof post about <a href="http://social-proof.org/post/20093160152/missed-connections-the-two-types-of-men-you-meet-in-sf">Missed Connections in San Francisco</a>. While we had initially satirized this kind of behavior, there was something endearing and beautiful about it that we really wanted to work with. Surely there had to be a better way for San Franciscans to post their missed connections other than Craigslist's paginated and lifeless listings, right?</p>

<div class="lemphasis">
<b> It's More About What You Take Out of the Product </b>
</div>

<p>I was swiftly able to set up a public blogging structure via Rails with all sorts of crazy features. Once we figured out what was even technically feasible, it was time to make the difficult decisions that lead to the perfect product recipe.</p>

<p>This required us to take a step back and ask ourselves what the most important aspects of our product would be. Here was what we came up with:</p>
<ul>
	<li>A story is a concise and meaningful snippet about love in San Francisco.</li>
	<li>A story belongs to a neighborhood. Neigbhorhoods would add context and flair to potentially open-ended and vague snippets. </li>
	<li>Stories should be signed somehow to indicate that they were written by a person. </li>
	<li>All stories should generally look consistent, and the content itself should be emphasized the most (this informed the decision right off the bat to omit any kind of imagery).</li>
</ul>

<p> After deciding to focus on these four things as our guiding principles, it helped to inform the following product decisions</p>

<ul>
	<li><span class="lemphasis"><b>250 character limit</b></span>: Twitter's 140 character count forces people to choose their words carefully when composing a tweet. This rationale resonated with us because we wanted our stories to be short and sweet vignettes instead of long drawn out sagas. Since 140 characters would be a bit short to tell a complete story, we decided to increase it to 250 characters. This limit typically allows enough for 2-3 complete sentences and definitely proved to be our sweet spot number. </li>
	<li><span class="lemphasis"><b>Anonymous</b></span>: Since we wanted the stories to be attributed to someone, we created an input field for signatures. Stories were automatically attributed to "Anonymous," but users could go in and change this themselves if they wanted to create an alias for themselves. (Sidenote: We got some really interesting personas like "Smitten in Soma" and "Blogbabe" out of this feature). </li>
	<li><span class="lemphasis"><b>User Authentication for Creating Stories</b></span>: Surely it would cut down the amount of people willing to post by introducing something as "friction-y" as a sign up flow, but we <em>wanted</em> this tiny bit of friction. Even though user information is never displayed on our site, we hoped that the idea of actually entering an e-mail address and password could be our quality filter (and keep away some of our trolls!). You're not nearly as likely to spam a website that has your information tucked away somewhere, now are you?</li>
	<li><span class="lemphasis"><b>No Time Stamps</b></span>: This was an interesting last minute decision. Displaying a time stamp for any piece of content on the internet is pretty standard and was easily available in our database for stories. After formatting timestamps to look nice and clean, we asked ourselves if we even really needed them. The answer was a deliberate no. Stories served to create a mosaic of love stories and needed to feel timeless. Including time stamps based on recency did not really move this goal forward in any way. In fact it could draw unnecessary emphasis on the recency of stories and make the site eventually feel dated. </li>
	<li><span class="lemphasis"><b>Likes</b></span>: Since we had pulled out comments, we wanted to have some way for users to get/leave feedback on stories. Likes seemed to be the obvious action (especially since the heart goes so well with our brand), but how should they work? So many people have contacted me since the site launched saying "LOL, liking is broken. You can like things more than once!" Friends.. this decision was intentional. Since the process of posting requires signing up, we didn't want the same flow to exist for likes because it could prevent initial engagement with the stories themselves. In retrospect, working with "cookies" could have fixed this problem to an extent, but it didn't even seem like the end of the world to allow users to like certain stories more than once. The more engagement the better for a brand new product! </li>
</ul>
<br />
<div class="lemphasis">
<b> What's Next </b>
</div>

<p>And there you have it, a few anecdotes of some of the product lessons Sabrina and I learned during our hackathon. I must say that I'm thrilled that we kept things super simple  for the launch because it feels so good to actually have people coming to us with feature requests! </p>

<p>I'll leave you guys with a preview of what's to come: </p>
<ul>
	<li>Adding Ajax to likes (this way the page won't annoyingly refresh everytime that you post).</li>
	<li>We noticed loads of people were screenshotting stories and sharing them on twitter, so it would be cool to add some landing pages.</li>
	<li>ILoveYou___.com at another location near you? Who knows!</li>
</ul>