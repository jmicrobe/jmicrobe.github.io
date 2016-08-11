---
layout: post
title: On data presentation & visualization
---

I recently attended a workshop by [Edward Tufte](https://www.edwardtufte.com/tufte/index), a very well-known statistician, author, and data scientist. If you haven't seen his books they are quite inspiring and frankly gorgeous to look at and explore. The workshop was focused on data presentation and visualization. I'd like to share some of my musings on the subject, from a bioinformatics perspective...

## Presenting data
---
There are a lot of questions you need to answer when you're preparing to present scientific data. Who is your audience? How much time do you have? What kind of media do you have to work with? What message are you trying to convey with the data?

<p align="center">
<img src="https://cloud.githubusercontent.com/assets/17626538/17566500/7b75f708-5ef0-11e6-96ba-54881b5d2bfe.gif">
</p>

Edward Tufte is an outspoken opponent of the PowerPoint format, and the examples he gives in his books (namely *Beautiful Evidence*) are sound. If the data you present to your audience is going to be used to help them make a judgement on say, safety procedures regarding the impact of damage from errant debris on a space shuttle - a PowerPoint pitch is terrible.

However, in academia I'd argue that a *pitch* is the best way to present research at a conference, and it should be treated as such. I was recently at the [Pacific Northwest Women in Science Retreat](http://wsrpacificnorthwest.com/) and learned a lot about taking lessons from actors and translating them to presenting data ([thanks Nancy Houfek!](http://www.nancyhoufek.com/index.shtml)). One thing that really stuck with me is the importance of **telling a story** when you present. I realized that the most memorable presentations I've seen are ones where it feels more like the presenter is sharing a story of their work, rather than reading off details of their experiment. This kind of brings me back to a quote from Tufte: *"No matter how beautiful your interface is it would be better if there were less of it"*. For a talk, less details are better. A good talk should leave the audience with lots of questions - questions that can be answered in reading the paper on the study, or viewing the poster, or talking to the researchers.

## Visualizing data
---
Depending on the mode of presentation, your visualizations may be different. Tufte presents a few principles of visualizing data that I think are important.

### **Get rid of chartjunk**

Chartjunk is just what it sounds like, clutter on a data visualization. I'd like to think this is largely a thing of the past - from the days when flashy software for data visualization was first introduced. Just because you *can* make your pie chart look like an actual pie doesn't mean you *should*. Actually if you're going to use a pie chart you might as well...

One of my favorite terrible chart examples provided by Tufte in *The Visual Display of Quantitative Information* is this piece of work from the 1970's that somehow tries to illustrate college enrollment by age group.
<p align="center">
<img src="https://cloud.githubusercontent.com/assets/17626538/17579280/1aa31908-5f48-11e6-999b-d9e4eef29de2.png">
</p>

You know if you turn it on it's side it almost looks like one of those vase/face illusion graphics...

Additionally, chartjunk reminds me of the book *The Design of Everyday Things* by Donald Norman. This book is a classic that most material designers read, but I think it easily translates to the design of everyday *data* things. The central idea Norman presents is of *user-oriented design* and the book explores ways in which design can be improved to optimize the use of an object by the user. My favorite example of this is a "Norman door". If you've ever encountered a push/pull door that isn't intuitively designed, in a way that has cause you (the user) frustration in discovering how to operate it...that's essentially a Norman door. This video from Vox is a great discussion on the subject.

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/yY96hTb8WgI" frameborder="0" allowfullscreen></iframe>
</p>

Back to data. We don't typically *operate* data like we would a door, or a teapot (well unless you're making a [Shiny visualization with R](http://shiny.rstudio.com/)) - but we do interact with it. [This post over at Dataremixed.com](http://dataremixed.com/2016/04/the-design-of-everyday-visualizations/) highlights how data visualization can borrow from Norman's ideas about user-oriented design. Namely that:

1. **Good visualizations are discoverable and understandable**

Something I'm sure Tufte would agree upon. Tufte encourages you to trust the intelligence of your audience and let them explore your data. Using Norman's principles you can make this work by designing your visualization in such a way that your viewer doesn't need a guide to understand how to read the data.

2. **Absolute precision isn't always necessary**

This goes back to data presentation. In academia, there's a certain hierarchy that should be followed - with higher precision expected in something such as a report or print article. If you're pitching your research at a conference it may be a good idea to sacrifice precision for better readability.

### **Minimize data ink**

Along the lines of chartjunk Tufte introduces the concept of the "data-ink ratio". Essentially the best data-ink ratio is one where all of the ink in an image represents only useful data. While some of Tufte's suggestions feel like extreme minimalism, I thought this example from [Info-Viz Wiki](http://www.infovis-wiki.net/index.php/Data-Ink_Ratio) highlight's this concept well:

<p align="center">
<img src="https://cloud.githubusercontent.com/assets/17626538/17597060/1959ed68-5fa9-11e6-95d1-61d65d408942.png">
The plot above has a low data-ink ratio and contains unnecessary lines and shading that detract from the data.

<img src="https://cloud.githubusercontent.com/assets/17626538/17597062/1b4ab954-5fa9-11e6-88f8-7680b4fafbb7.png">
</p>

The plot above has a high data-ink ratio, and minimizes the amount of visual distraction in the figure. I really like the horizontal lines within the bars that make it easy to read and compare percentages across the figure.  

## Data visualization Tools
---
Over the past year I've been learning how to analyze data using the [programing language R](https://www.r-project.org/). It's hard to say what my favorite thing about R is...that it's open source? That there's an [excellent graphical user interface](https://www.rstudio.com/)? That there is an active community of developers on a plethora of packages?

One of my favorite packages in R is ggplot2, and the slew of other data manipulation packages from [Hadley Wickham](http://hadley.nz/). In my (humble) opinion ggplot2 improves upon the base graphics in R, but more importantly for me it has been easier to write understandable code to produce my figures. If you need convincing, [read this list](https://github.com/hadley/ggplot2/wiki/Why-use-ggplot2) on why you should use ggplot2.I should probably do an entire write-up on using ggplot2 with bioinformatics data, but for now I'll just share a few links to things I found helpful:

- [Swirl](http://swirlstats.com/): The **best** way to get acquainted with RStudio. Swirl is a package that teaches you R, in RStudio. It's amazing. Seriously.
- [RClub at University of Oregon](https://blogs.uoregon.edu/rclub/): Going to their workshops not only improved my data wrangling skills but the folks who run RClub are a great resource.
- [Colorbrewer2](http://colorbrewer2.org/): This is a GREAT tool for picking colors to use with ggplot2 graphics. It includes color picking to accommodate color blindness, something really important to consider when creating data visualizations.
- [Cookbook for R](http://www.cookbook-r.com/): I used this site nearly every day when I took my first class that used R.
- [Cowplot](https://cran.r-project.org/web/packages/cowplot/vignettes/introduction.html): I often use this package with ggplot2 to create publication-ready graphics. The plot_grid() function makes it easy to combine plots on a gride.
