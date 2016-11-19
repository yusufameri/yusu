---
title: "How to add Rmarkdown to Your Jekyll Site"
layout: post
date: 2016-11-18
tag: [rmarkdown, r, jekyll, howto]
blog: true
#star: true
---

Note before we start: I found out how to do this myself from [this](https://github.com/jfisher-usgs/jfisher-usgs.github.io/blob/master/Rmd/2012-07-03-knitr-jekyll.Rmd)
github tutorial.

I have been using R for a few months now and one of the best things about it is
it's most popular IDE, Rstudio. In Rstudio, you can write both your code and
comments in the same file via a markdown-style file called Rmarkdown. You can
then use a built in compiler (knitr) to "knit" your Rmarkdown file into
a more useful file format such as a .html or .pdf file. This is really great for
data science projects as it makes sharing projects much easier and also makes
it easy for people to reproduce your code.

## The Problem
Unfortunately, jekyll does not allow you to upload .Rmd files or .html files
directly as a post. Therefore, we need a way of converting our original .Rmd to
a .markdown (.md) file for jekyll to be able to process and make use of it.

## Step-by-Step
1. Create the following directories in your jekyll parent directory:
* `_source`
* `figs`
2. Create an empty Rscript file and place in your parent directory
{% highlight raw%}
touch rmd2md.R
{% endhighlight %}
3. Paste the following code in that file
{% highlight r%}
KnitPost <- function(input, base.url = "/") {
  require(knitr)
  opts_knit$set(base.url = base.url)
  fig.path <- paste0("figs/", sub(".Rmd$", "", basename(input)), "/")
  opts_chunk$set(fig.path = fig.path)
  opts_chunk$set(fig.cap = "center")
  render_jekyll()
  knit(input, envir = parent.frame())
}
{% endhighlight %}
4. Copy and paste your .Rmd file into the `_source` directory.
You are going to have to rename the file to the proper jekyll format.
If your original file was called:
{% highlight raw%}
your-file-name.Rmd
{% endhighlight %}
You will have to rename it to.
{% highlight raw%}
YYYY-MM-DD-your-file-name.Rmd
{% endhighlight %}
where the `YYYY-MM-DD` portion of the file corresponds to the current (or relevant) date.
5. Open a R Console (I use Rstudio) and run the function
{% highlight r%}
KnitPost("YYYY-MM-DD-your-file-name.Rmd")
{% endhighlight %}
Make sure your working directory is set to the
parent directory of your jekyll site.

---

Your file should now be knit into a `.md` file and be in your parent directory. Move the file to your `_posts` directory. If you look in the `figs` directory, there should be a directory that was created that has the .png images from plots that were generated from your .Rmd file.

---

I hope you found this tutorial useful. If you have any
questions comment below and I will try my best to get
back to you.
