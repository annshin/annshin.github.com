---
layout: article
title: How to build your personal blog using GitHub Pages + Jekyll
tags: pseudo-tutorial-random
---

`Beginner level`{:.success}

**My (your ?) aim**

Build a personal blog with a `xxx.github.io`-format URL.

**My (your ?) current status**

I searched on the web and heard of words like [GitHub pages](https://pages.github.com), [Jekyll](https://github.com/jekyll/jekyll), but... well, I still don't know what they are exactly & how to use them. I'm not experienced in website building, but it's actually ~~quite~~ very easy.

**Now:**

1. I'd like to know a bit more about GitHub Pages first: [press here](#faq){:.button.button--primary.button--pill}

2. I just want to create my blog *now*: [step-by-step tuto](#tuto){:.button.button--primary.button--pill}

3. There is nothing I want here. I'm leaving.

## <a name="faq"></a>About GitHub Pages
(It's certainly not exhaustive, I just wrote about what I've looked at and selected the parts I found useful)

### What's GitHub Pages ?

I quote from [GitHub Help](https://help.github.com/en/articles/what-is-github-pages):
> [It] is a static site hosting service designed to host your [...] pages directly from a GitHub repository.

There is a hard limit of 1GB:
> The size of the published site should be [< 1GB.](https://help.github.com/en/articles/what-is-github-pages#usage-limits)

### Can I have several GitHub pages ?

Just one with `yourusername.github.io` format.

But there can be project websites like `yourusername.github.io/project1`, `yourusername.github.io/project2`...


## <a name="tuto"></a>How to build my blog step-by-step ?

*Note: This is just one way to make things work.*

### 1. Create a specific GitHub repo

![](/assets/images/tuto-random/2019-04-08-blog-1.png)

*Notes:*

* You could actually use `yourusername.github.io` as repo name, I used `yourusername.github.com` and it also works.

* If your GitHub account is:
  * Free: your repo of GitHub Pages should be **public**.
  * Pro/Team/Enterprise Cloud/Enterprise Server: your repo can be public or private.
More info [here](https://help.github.com/en/articles/what-is-github-pages).

* If you want more info on: how to [create a repo in GitHub](https://help.github.com/en/articles/create-a-repo).


### 2. Clone your repo to local folder

Using HTTPS:

`git clone https://github.com/yourusername/yourusername.github.com.git`

### 3. Install Jekyll + choose a theme

1. **Install Jekyll + bundler**

   `gem install jekyll bundler`

   If you don't have Ruby yet, here's a [detailed instruction](https://jekyllrb.com/docs/installation/).

2. **Create the blog**

   * If you want to create and use the basic template, you can: `jekyll new myblogname`

   * If you want to use a nice third-party template:

   1. Choose a template

      You can find plenty of nice free Jekyll templates by searching on GitHub, or you can have a look at [Jekyll Themes website](http://jekyllthemes.org).

      Actually I found that the [default template](https://github.com/jekyll/minima) is quite simple, and the one I'm using is [TeXt](https://github.com/kitian616/jekyll-TeXt-theme), so I'll take this one as example :satisfied:

   2. Clone or download the theme repo.

   3. Copy the files that you need to your `yourusername.github.com` repo. 

      The folder structure is like this:

         <img class="image image--xl" src="/assets/images/tuto-random/2019-04-08-blog-2.png"/>

         * Folders such as `docs`, `screenshots`, `test` are not needed for your blog to run.

         * `_posts` is where your posts will be stocked.

         * `_layouts` contain the *template* of different pages that you could directly use.

      If there is a license/notice to be included, please don't forget to keep them :relaxed:

   4. Run `bundle install` to install the dependencies. 

   It's now OK for the basic setup.

3. **Write a new Post**
   
   1. Create a new file with a name formatted like `YEAR-MONTH-DATE-name-of-the-file.md`.

      The template need a correctly formatted name to be able to recognize the infos.

   2. Start to write...

      An example of content:

      ```markdown
         ---
         layout: article
         title: Explain how to build a personal blog to my Snorlax
         tags: pseudo-tutorial-random
         ---
         
         Hello world !
      ```

      * `layout` corresponds to the various layouts in the folder `_layouts`.

      * `title` is the title actually displayed.

   3. That's all.

4. **Configure your profile**

   Just modify the parts you want in `./_config.yml`.

5. **(Optional) Add a new Page**

   For instance, if I want a new Page named `Gallery`.

   1. Create a file name `gallery.md` and save it in the main folder (or another one, you can change the configurations after if you want to).

      For instance, I can use the `article` layout for this page:
      ```markdown
         ---
         layout: article
         ---

         My gallery.
      ```

   2. Open the YAML file `./_data/navigation.yml` and just add the name of your page, for instance:

      ```markdown
        - titles:
         en      : &EN       Gallery
         en-GB   : *EN
         en-US   : *EN
         en-CA   : *EN
         en-AU   : *EN
         zh-Hans : &ZH_HANS  相簿
         zh      : *ZH_HANS
         zh-CN   : *ZH_HANS
         zh-SG   : *ZH_HANS
         zh-Hant : &ZH_HANT  圖片集
         zh-TW   : *ZH_HANT
         zh-HK   : *ZH_HANT
       url: /gallery.html
      ```

      (*Note*: If you want to test, avoid calling your test page "test".)

### 4. Test it in local

1. In your terminal: `jekyll serve`

   If you have an error (like me) saying that:
   > You have already activated addressable 2.6.0, but your Gemfile requires addressable 2.5.2. Prepending `bundle exec` to your command may solve this.

   Then:

   `bundle exec jekyll serve`

2. Open your browser and go to: `http://localhost:4000`

   Normally you should see your website built.

### 5. Just push it

If you want more info on [how to push to a repo using the command line](https://help.github.com/en/articles/adding-a-file-to-a-repository-using-the-command-line).

After some time (not very long) you should be able to see what you've seen in local at `yourusername.github.io` ! :sparkles:

---

Hope that it helped :smile: