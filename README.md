Blogdown source code
================
Sergi Ballestar

# Quick Tutorial on How to build a Hugos blogdown source code

First of all, we need to set some git parameters in our R Studio
terminal:

## 1\. Configuration set up

`git config --global user.name "sergiballestar"`

`git config --global user.email "xxxxxxx@gmail.com"`

## 2\. Cloning repo from GitHub

Then we need to clone the git repo were we will safely store our
blogdown source code. otherwise we might lose our code and have to start
from the very begining to edit anything.

`git clone https://github.com/sergiballestar/blogdown_source.git`

In case this was the last repo we worked with, a simple `git init` may
be enough.

## 3\. Do changes with R studio

Here comes the funny part. Before creating the new site we need to check
that all the packages are properly installed:

`install.packages("blogdown")`

`library(blogdown)`

`blogdown::install_hugo()`

### 3.1 Creating the new site

Now that everything is settled up, let’s begin creating a new site. I
would encourage you the check [HUGO’s
themes](https://themes.gohugo.io/). In this case we’ll go with one of
the most popular theme, [Academic by George
Cushen](https://themes.gohugo.io/academic/). Please mind that in this
case we chose `theme_example = TRUE` but you can set it to `FALSE`, if
prefered.

Let’s come back to R console (not the terminal):

`blogdown::new_site(theme = "gcushen/hugo-academic", theme_example =
TRUE)`

If your theme is not pre-installed in HUGO yet, you can try installing
it this way (please mind in this case [“Creative
portfolio”](https://themes.gohugo.io/hugo-creative-portfolio-theme/)
by Kishan B theme was chosen as example):

`install_theme("kishaningithub/hugo-creative-portfolio-theme",
theme_example = TRUE, update_config = TRUE)`

Once the `new_site()` was created check the diferent folders and add the
content you consider.

### 3.2 Preview

Use this commands to preview how your work will be seen (and to stop the
preview)

`serve_site() #preview`

`stop_server() #stop preview`

### 3.3 Build site

Once your site is finished, just use this command to build it:

`build_site()`

you can change this options, check the information package for more
info:

`build_site(local = FALSE, method = c("html", "custom"), run_hugo =
TRUE)`

## 4\. Check new files were detected & Adding all changes

Let’s come back to the terminal:

Adding files:

`git add -A`

Check if new files were added:

`git status`

## 5\. Commiting

Write here the changes you made

`git commit -m "blablabla"`

## 6\. Push

Push it up (master branch as example)

`git push origin master`
