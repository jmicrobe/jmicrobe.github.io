---
layout: post
title: science hack day portland part II, the hackening
---

This is the second part of my write-up on what it was like organizing and participating in Science Hack Day Portland 2016. As an exciting sidenote and excuse, this is terribly overdue because I recently graduated, got a job, and relocated. More on that later!

Where were we? At the end of the first night things were winding down - our competent yeast cultures and CRISPR bacteria were warming up, the 3D printer was raging on, and I was exhausted. I pitched my tent and went to bed.

Guests slowly started streaming in the following morning, and I helped get our DIY coffee station up and running. Saturday was when the magic happened. Groups started to dig in and bring together their hardware and software ideas. I helped design some 3D printed medals on the fly, and another science hacker (who I later found out was a quilter!) helped sew lanyards to hold them.

### Here's where I'm going to tell you about the project I worked on, and how it failed.

That sounds harsh, but as a scientist I'm really used to failure and it's not at all a bad thing (particularly in the discovery phase). My first failure was to **pick out something I already do**. While it was nice to work with something familiar to me, and get the chance to teach my team mate about it, I really didn't get out of my comfort zone. I also **didn't take advantage of the awesome toys and supplies that were donated**. While everyone else was hacking their raspberrypi I was doing what I do every day at work.

If it's not obvious, the project I chose was using bioinformatics - more specifically taking open data from [NASA Genelab](https://genelab.nasa.gov/) on a 16S rRNA marker gene survey of the indoor microbiome of the International Space Station. With my partner we were interested building some fun, hopefully interactive visualizations using this data. This turned out to be really challenging for one big reason. **Neither of us were familiar enough with the cloud computing resources necessary to work with this data in such a short amount of time**.

This is where I'd like to spin this in a positive direction - my partner and I had a crash course in tools like [Docker](https://www.docker.com/), [AWS](https://aws.amazon.com/), and [Digital Ocean](https://www.digitalocean.com/). That morning we both scrambled between getting AWS configured, to ditching that and getting a hook-up on some credits to spin up a really powerful Digital Ocean drive, and the mess ended with learning how to configure a docker image that contained the bioinformatics program [QIIME](http://qiime.org/index.html) along with enough storage to handle the raw 16S dataset from GeneLab.

I'm still a bit new to bioinformatics, but from my experience that day was very similar to the challenges I face with my day-to-day work. I was only half-joking with my previous PI when I said that **90% of bioinformatics use is figuring out how to install programs**.

Anyways the day went on and in between bouts of yelling at my computer screen I walked around to observe and help out other projects. I especially enjoyed being a guinea pig in Jean & Marlene's project to build a temperature-sensing glove for Reynaud's syndrome. I stuck my hand in a freezer for 30 minutes FOR SCIENCE!

<blockquote class="twitter-tweet" data-lang="en"><p lang="ro" dir="ltr">Sensor prototype for Raynaud&#39;s disease monitoring. <a href="https://twitter.com/hashtag/pdxscience?src=hash">#pdxscience</a> <a href="https://twitter.com/science_hackPDX">@science_hackPDX</a> <a href="https://twitter.com/hashtag/openscience?src=hash">#openscience</a> <a href="https://t.co/ALbl84Oa15">pic.twitter.com/ALbl84Oa15</a></p>&mdash; Robin Champieux (@rchampieux) <a href="https://twitter.com/rchampieux/status/784937645805678592">October 9, 2016</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Other fun things included Max showing folks how to develop black & white photographs with vitamin C and coffee, a pipette-ejecting contest, a Hack Oregon confetti cannon, an LED lamp that projects a rainbow double helix and even pumpkins that light up LEDs when you touch them. **It was freaking amazing**.

### And now for a bit of reflection

I learned so much from Science Hack Day - about my community & local scientists, about the logistics of organizing such an event, and a bit about my own capabilities when I scoot out from my comfort zone! One thing I hope to see at the next Science Hack Day is more prep and even infrastructure geared toward data science with large data sets. Some of the Portland organizers are already pushing for this - and recently hosted an [Open Data Day](http://opendataday.org/) complete with tutorials on metadata and web scraping to accompany the event. We are also already in the planning stages for Science Hack Day Portland 2017, and are working towards more smaller events leading up to it. 
