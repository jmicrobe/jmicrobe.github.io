---
layout: unlisted-page
---
# Getting started on github: Building a static site using Jekyll
This tutorial will introduce you to some basic concepts of git, Github pages, and Jekyll in order to make a simple personal website.

**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Dependencies](#)
- [What's a repo?](#)
- [Overview of git & Github](#)
- [Github pages & Jekyll](#)
    - [Fork the sample site](#)
    - [Clone the sample site](#)
    - [The Jekyll file structure](#)
    - [If you are working locally:](#)
    - [If you are working from Github online:](#)
- [Moving on with other themes](#)
- [Wrapping up](#)
- [Links](#)

## Dependencies
+ [Git](https://git-scm.com/)
+ [Github](https://github.com/) account, I suggest unlocking a [student developer pack](https://education.github.com/pack)
+ [Jekyll](https://jekyllrb.com/docs/installation/)
+ Your favorite text editor (I use [atom](https://atom.io/))

## What's a repo?
With git & Github a repo (repository) is a folder that represents a project and all of the files and subdirectories involved. Have a look at the repo we'll be cloning today, which includes a starter website: **[https://github.com/jmicrobe/getmicah](https://github.com/jmicrobe/getmicah)**

## Overview of git & Github
Git is a version control system commonly used for (but not limited to) software development. It's a powerful tool that can track changes to a project, and allows for non-linear workflows. Git is fast and comes installed on many unix-based systems.

While git is initialized locally, you can push your projects to remote websites like Github (though there are others). Github is great for many reasons, namely that it can manage multiple collaborators on a single project, and it's great for building your online coding portfolio and presence. A great way to get started with Github is to build a Github page using Jekyll.

## Github pages & Jekyll
Github allows users to host their own website using a special github pages repo. In this case it contains all of the files to build the user's website. Each user is allowed one Github pages site, and unlimited project pages (not included in this tutorial). This repo must be named username.github.io, and the website lives at that same address.

**Jekyll** essentially builds your website based on a specific directory structure. Jekyll generates a **static site**, which is in contrast to a dynamic website. Static sites are great for simple, personal webpages that aren't intended to be interactive. Jekyll is baked-in to github pages. In fact, you can launch a Jekyll personal site on github without installing Jekyll locally. In this case the downside is you can't build, test, and debug your site before pushing it online.

## Fork the sample site
In your browser, go to the [sample site repo](https://github.com/jmicrobe/getmicah) and fork it to your own account. From your account, click on the repo and go to its settings. Change the repo name to yourusername.github.io. This will tell Github to set it to your personal page. To check that this worked, go to the web address yourusername.github.io. It should display the sample site.

#####At this point you have some options. Since the site is already built, you can edit any of the files directly on Github in your browser. Skip to [The Jekyll file structure](#) if you plan to work this way.

## Clone the sample site
If you're [3l33t](http://www.urbandictionary.com/define.php?term=3l33t) of course you're going to want to edit your website locally in a text editor, build your site with Jekyll and push changes to Github. This is great practice for m@d command line skillz. I digress.

In terminal pick a top directory to place your website folder:

`$ cd your/preferred/directory`

Now clone the sample site repo here as a new folder. The address to clone from can be copied from the repo page, under "Clone or download"

`$ git clone https://github.com/yourusername/yourusername.github.io.git`

*Note: if you have problems here you may not have git installed, or you may have to use an SSH address and/or generate a SSH key*

I like to sanity check and see that the folder copied here with `ls`, then move in to it:

`cd yourusername.github.io`

If you `ls` again you should see your website directory structure! Since everything is all here, we should be able to build and preview this sample site. If you have properly installed Jekyll type in:
`jekyll serve`

You should get an output that ends with something like this:

`Server address: http://127.0.0.1:4000/`

`Server running... press ctrl-c to stop.`

Copy and paste that server address into your browser to preview your website. This is how you'll preview and debug your website build with Jekyll prior to pushing your site to Github.

## The Jekyll file structure
Jekyll builds your site based on the contents within a specific site structure. They explain this structure best [on their website](https://jekyllrb.com/docs/structure/), but we'll cover a few specific elements that you may want to edit:

### \_data/navigation.yml
This document is in yml, or YAML format. Notice that it represents the links located on the top navbar of the website. Feel free to edit or add links to this document, following the same format.

### \_includes/header.html
This document is in html format. \_includes are for re-usable elements, like a header in the case or a footer. You'll notice other files like index.html have a line of code near the top that looks like:
`{% include header.html %}`
Which tells Jekyll to include that header file.

Another thing to note about this file is that it contains some special tools:

`<div class="blog">`

References the website's CSS document located at `/assets/css/main.scss`. If you aren't familiar with CSS it's a way of separating code from content on your website. Have a look at `main.scss` and find the entry for `blog`. You can see that this element sets a few font-related settings.

Back in `header.html` you'll also notice a syntax already hinted at:

`{% for item in site.data.navigation %}`

This syntax is known as **Liquid**, Jekyll's templating language. Have a look [here](https://jekyllrb.com/docs/templates/) if you want to learn more about Liquid. In this case it's simple to see that the above code sets a for loop, that reads the `_data/navigation.yml` file and creates the following:

`<a href="{{ item.url }}">{{ item.title }}</a>`

Which is a little bit Liquid, and a little html. Essentially this looks at `navigation.yml` and creates links for each of the entries. Since this is the header file, any page that uses `{% include header.html %}` will have these links at the top.

### \_layouts/

These are templates that are used to wrap a page on the website. If you're sticking with the sample theme you shouldn't have to modify these files, but you'll notice that `default.html` is used in the other two layouts `about.html` and `posts.html`. `default.html` includes a few bits of metadata and control code under `<head>`. Additionally, you'll notice more of the Liquid syntax in all three of the layout files. This helps control how content is displayed. If you want to modify the format of your "about" page, or you blog posts, try editing these files.

### \_sass/
Sass is basically a fancier version of CSS. The files in this directory, similar to `/assets/css/main.scss` in that they set some of the visual formating for content. I'm not (yet) a CSS/sass expert so I typically leave these alone.

### assets/
We already looked at `/assets/css/main.scss` but the assets folder also contains `img`, which is home to a file called `favicon.ico`. This is the little image that is displayed for your website at the top of a browser window. You can replace it with another .ico formatted image if you'd like. There are several free galleries online, but also generator tools that can convert things like .jpg or .png images into a favicon. Just make sure your new image has the same title.

Additionally, if you'd like to add a photo to your site - say on your "about me" page, you can add that image to the `/assets/img/` directory (and then use html or other code to have it display on the page you want). Since this directory doesn't start with an underscore, like `_sass` or `_layouts` Jekyll won't have a fit trying to build your website if you have extraneous stuff in here.

### .gitignore
This file is how you can tell git to ignore certain files/directories. Notice in this file that `_site` and `_drafts` are ignored. This means git won't track changes in these directories, and when you push the directory to github these directories are excluded from showing up in your repo.

### CNAME
Notice that this file is empty. If you happen to have a custom domain name, you can enter it here (ie mywebsite.com). Once you've configured forwarding with your domain host it will set mywebsite.com to show your github page. This comes in handy if you take advantage of the domain hosting discount via the student developer pack!

### README.md and LICENSE
Both of these files are typically generated by default on Github. `README.md` is a markdown formatted file, and any file with this name will display on Github's repo page. In this case, it isn't displayed on the actual website, but shows up when viewing your repo. `LICENSE` is self-explanatory - this file lists the chosen license for the repository, which controls how your work can be used/shared/distributed.

### index.html
By default index.html is the first page displayed on the root your website (so going to yourusername.github.io will show this page). For the sample site, this page follows the default layout, includes `header.html` and uses Liquid/html to display blog post titles and their links. Feel free to play around with this page. You can add some text with html, include a picture, or for more advanced stuff try adding another list like site.posts such as site.links (in the same manner the posts are pulled).

### cv.html
Here I've written a super simple, html-based cv template. You can fill it in with your info as-is, or tweak the format by modifying the `div class=portfolio` in the `/assets/css/main.scss` file. You could even re-do this page to just be a link to a pdf of your cv (by editing the cv url in `/_data/navigation.yml`). You could even change the file to cv.md and write your cv in markdown format (which is simpler than html).

*Note: for this theme if you switch your cv to markdown you may need to follow the directory format of the `about` page. See below...*

### me/
Under this directory is a file called `index.md`. If you open it you'll see this is the contents of the `about` page, written in markdown format. Revisit the `/_data/navigation.yml` document and you'll notice that the link for `about` points to the url `/me`. This tells Jekyll to go to that folder, and since the only file within is `index.md`, this is the page that is displayed. Edit the contents of `index.md` to fit your liking. If you need help with markdown formatting [here's a cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) (which includes how to embed video or include a picture).

### \_config.yml
This is a powerful, important file for Jekyll that stores your site's configuration info. You'll want to edit the `name:` and `description:` fields for yourself but everything else can stay the same. To see what other things you can configure see [Jekyll's guide here](https://jekyllrb.com/docs/configuration/).

### \_posts/
Here's where you put your blog posts, in markdown format. In this directory you'll see that I've left the original theme owner's content - have a look at the files to get a sense for the markdown format. Also note the naming convention for the files. Jekyll requires this format in order to build and reference your blog posts. Feel free to create a new file with a new blog post to celebrate the occasion. For more info on blogging see [Jekyll's guide here](https://jekyllrb.com/docs/posts/).

*Note: you can create a directory called \_drafts to store drafts for your blog post. Since \_drafts is in the .gitignore file they will not be visible on Github.*

## If you are working locally:
Once you are done editing your site files you can preview the changes by entering the following in terminal, while in your site's main directory:

`jekyll serve`

And as before, copy the server address into your browser. If you like what you see, and you're ready to push your site to Github we'll first check git's configuration, commit changes and push this verison to the online repo:

To set your user name:

`git config user.name "User Name"`

OR

`git config --global user.name "User Name"`

The first option sets your user name only for the current directory, the second option sets this for your global user settings (my preferred option).

To confirm this:

`git config user.name`

should return:

`User Name`

Do the same thing with your email address. Ideally the one associate with you Github account:

`git config --global user.email "username@example.com"`

Since we cloned this repo it should be automatically linked to the remote Github address. To verify this enter:

`git remote -v`

This should return something like:

`origin	https://github.com/username/username.github.io.git (fetch)`

`origin	https://github.com/username/username.github.io.git (push)`

If the address is incorrect you can remove 'origin' with:

`git remote remove origin`

and then add the correct link to your github.io repo:

`git remote add origin https://github.com/username/username.github.io.git`

Now that we have our git configured, we can commit these changes. A commit is a way of setting a version to your files. Technically any time you make changes to a file you should commit them, in order to track your version control.

First we need to add our directory to git's staging area. This tutorial won't go into too much git detail, so I highly suggest checking out the online book [Pro Git](https://git-scm.com/book/en/v2), as it has a simple guide to getting started with git.

`git add .`

Now we want to commit all of our changes:

`git commit -m "First commit"`

Note that -m stands for message. Here we're making our first commit, but for other commits a short, specific message is helpful if you need to backtrack to a specific version of your edits.

Now we're ready to push these local commits to our "remote origin", which lives at the Github repo online:

`git push origin master`

Again, I'm leaving out some details here, but essentially we're pushing the "master" branch (in this case the one and only branch of the project we're working on) to our online repo.

If everything worked you should be able to visit your repo page on Github and see the changes you've made. You should also be able to visit your website (username.github.io) and see your site up in action. Sometimes this can take a minute or two for the Github servers to update.

## If you are working from Github online:
To edit a file simply click on it from your repo page. On the right-hand site you should see a little pencil icon to click in order to open the file editor. In the file editor you can make your changes, and in order to save them you must "commit changes" each time. As previously mentioned, it's helpful to give a short, descriptive message with your commit so it is easy to return to that version.

In this case you aren't "launching" your site but rather publishing changes incrementally. **This option works best if you just want to write and publish a new blog post, without working with a draft.**

## Moving on with other themes
This guide uses a very basic, minimalist theme to avoid a lot of the tweaking more design-heavy sites might need. But there are **numerous** themes available for Jekyll (see [here](http://jekyllthemes.org/) and [here](https://jekyllthemes.io/) for examples). If you'd like to try out a different theme but keep some of your original content the process isn't as simple as say, changing a wordpress blog theme. However it's just a matter of copying the right data over to the new theme repo. [Here](http://stackoverflow.com/questions/31327045/switch-theme-in-an-existing-jekyll-installation) are some instruction options posted on Stack Exchange that I thought were helpful.

Personally I found it easy enough to make a "practice" website, then just overwrite everything using a new theme and start fresh.

## Wrapping up
I'm still new to Jekyll so if you catch mistakes in this tutorial or have problems do let me know. I think it's a great exercise on getting started with Github, and is good practice for learning new coding languages on the fly (my last front-end web development experience was making an html site for my favorite pokemon characters). I've collected all of the links into the section below for easy reference.

## Links
+ [Git](https://git-scm.com/)
+ [Github](https://github.com/)
+ [Jekyll](https://jekyllrb.com)
+ [Atom](https://atom.io): Github's friendly text editor.
+ [Jekyll file structure](https://jekyllrb.com/docs/structure/): Explains the file structure for using Jekyll.
+ [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet): A handy guide for writing in markdown.
+ [Jekyll \_config.yml](https://jekyllrb.com/docs/configuration/): Explains the Jekyll config file and what values you might add to it.
+ [Jekyll Blogging](https://jekyllrb.com/docs/posts/): Explains how Jekyll handles blog posts.
+ [Pro Git](https://git-scm.com/book/en/v2): A great guide for getting started with git. A must-read if you plan on using git in command line.
+ [Jekyll Themes](jekyllthemes.org): A nice gallery of (mostly?) free Jekyll Themes.
+ [JekyllThemes.io](https://jekyllthemes.io/): A gallery of free as well as premium Jekyll Themes.
+ [Jekyll.tips](http://jekyll.tips/): Short, handy video tutorials that cover beginner and advance Jekyll use.
