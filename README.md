# Instructions to update website 
*written by Amelia for Alex :-)*

**These instructions are for updating the LEAP group website found at [https://life-epi-psych.github.io/](https://life-epi-psych.github.io/).**

The website is built using GitHub pages, Jekyll and a theme called Bulma Clean. Don't worry if that means nothing to you - it's actually pretty simple to update now it's all set up! And I'll walk you through how to do that now.

## Run website locally

We want to be able to make changes to the website and check that it works before deploying it to the world wide web. To do this we want to be able to run the website locally. This is essentially the same view as what you see at https://life-epi-psych.github.io/ but instead we are viewing it on our local network by going to http://localhost:4000.

1. Clone this repo to your computer. I think you know how to do this, but if not see some instructions [here](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).

2. Check you have all the necessary programs installed on your computer to be able to test the website locally. Follow the instructions for steps 1. and 2. [here](https://jekyllrb.com/docs/) to install:
 - all [prerequisites](https://jekyllrb.com/docs/installation/)
 - jekyll and bundler gems by running `gem install jekyll bundler` in the terminal

3. Run `bundle exec jekyll serve` in the terminal. Fingers crossed no error messages appear (if they do and you're stuck, give me a shout). If that works you should be able to view the website locally by going to  [http://localhost:4000](http://localhost:4000) in your browser.

## Making changes to the website

1. **REMEMBER TO GIT PULL BEFORE MAKING ANY CHANGES!!!!** `git pull`
  
3. First let's tell you where everything is and what it does.

- [_config.yml](_config.yml) is the configuration file. It's where we can put default values too (to save you putting them on the header of each page). 

- [index.md](index.md) is the landing page of the website.

- [pages](pages/) contains markdown files of all the pages you see in the top navigation bar.

- [_data/navigation.yml](_data/navigation.yml) gives the layout and order of those pages in the top navigation bar.

- [_posts](_posts/) contains markdown files of all the posts that appear in the [News](pages/news.md) tab. **Important to use the correct syntax for naming files in this folder. "YYYY-MM-DD-name-here.md"**

- [people/](people/) contains a markdown file for each person. In the "People" page when the "i" icon is clicked on next to each person it will navigate to the page on that person saved in the "people/" folder. Eg. I made one for you called "alex_kwong.md". 

- [assets/images/](assets/images/) is where I've saved any images you want to display.

- [_data/callouts.yml](_data/callouts.yml) contains all the text and icons displayed on the Contact page.

2. Once you make any changes run `bundle exec jekyll serve` and view the site at http://localhost:4000. 

3. When you're happy with the changes you've made and you want to deploy them then simply git commit to the main branch. GitHub pages then automatically deploys this.
```
git add filename.md
git commit -m "remember to write a git commit message here"
git push
```

`git status` is also useful to see what changes have been made and if the file has been "git added", ie. staged.

## A note on themes

Something a bit annoying (and there's probably a better way round this). It's to do with GitHub pages.

If you're working on the site locally go into `_config.yml` and ensure that it looks like this:

```
theme: bulma-clean-theme
# remote_theme: chrisrhymes/bulma-clean-theme
```

**VERY IMPORTANT - WHEN YOU GIT COMMIT AND PUSH TO DEPLOY** go into `_config.yml` and ensure that it looks like this:

```
# theme: bulma-clean-theme
remote_theme: chrisrhymes/bulma-clean-theme
```

## Side notes

- headings of pages and any files with `.yml` are written in YAML. If you're getting errors about YAML code there are websites you can paste YAML text in and it will tell you what's wrong. You can also set up your text editor to do this.

- Pages can be written in markdown, html or a mixture of both. The flavour of markdown used is called kramdown. Please see more info about it [here](https://kramdown.gettalong.org/documentation.html).

- Please be aware that the names of the markdown files and their parent file names are in the site URL path. eg. https://life-epi-psych.github.io/people/alex_kwong is for the markdown file save in "people/alex_kwong.md".

