---
title: "Creating a Wonderful Blog Site with Hugo"
date: 2018-01-07T07:53:25+07:00
---

On one occassion, I was looking on Google for a guide to creating [GitHub pages](https://pages.github.com/). It turns out that it was a prettty easy process, providing that you have added a few elements to `index.html` in your repo's main branch (commonly known as `master`). After this, all you had to do was turn on **GitHub pages** in the repository settings, and your HTML site will be published at

```html
<github-username>.github.io/<repo-name>
```

>For an illustration, see my [HTML email template](https://github.com/f4ww4z/openmrs-template-gci) I worked on during [Google Code-in](https://codein.withgoogle.com), which is hosted by GitHub pages.

## Preface

You will need to know a few things before you go on implementing a static website builder framework (such as Hugo) and deploying it to your GitHub pages space. If you have already grasped the concept of Travis CI and static website building, you can skip to [Setting up Hugo](/posts/set-up-hugo#setting-up-hugo).

Prerequisites:

  - `git`
  - `hugo`
  - GitHub account

### Travis CI GitHub Pages Integration

One of the things I learned quickly about GitHub pages is that it can be continuously deployed from a Continuous Integration service. One extensively used CI for GitHub pages is [Travis](https://travis-ci.org). By adding a `.travis.yml` file in my repository, I am able to build a website using commands or rules defined in my `.travis.yml`. This means that I can use a website builder, and tell Travis to deploy it to my GitHub pages site.

>For more info on deploying GitHub pages with Travis, [see here](https://docs.travis-ci.com/user/deployment/pages/).

### Static website building

This blog site is built with **Hugo**. I use one of Hugo's collection of [supported themes](https://themes.gohugo.io/) in this blog called [temple](https://themes.gohugo.io/temple/). There is also another popular website builder called **Jekyll** (and GitHub actually supports it by default), however I still prefer Hugo due to its excellent performance and that Jekyll needs the extra step of setting up a RubyGemns environment in your local machine, to be able to extend your site with plugins. Moreover, Hugo takes a simple workflow and a straightforward means of setting up a site.

## 1. Setting up [Hugo](https://gohugo.io/)

Now that you have an understanding of using a CI service to deploy a website, let's learn on how to set up Hugo for our future blog site.

First, (if you haven't already) you will need to create a new repository on [GitHub](https://github.com) to host your blog. The name of this repository is typically

```html
<github-username>.github.io
```

To do this, log in to [GitHub](https://github.com), then down in *Your repositories* section, click **New Repository**.

<img src="/img/creating_new_repo.png" align="center" />

Next, go ahead and clone the new repository to your local machine. Next, navigate to your repo folder in your local machine.

#### Installing Hugo

For Linux systems that support snaps, you can install `hugo` by entering this command in your terminal:

```bash
snap install hugo
```

For Debian and Ubuntu (my current OS for this guide):

```bash
sudo apt-get install hugo
```

For macOS systems, use:

```bash
brew install hugo
```

>For more detailed *install* instructions, see [this official guide](https://gohugo.io/getting-started/installing) from Hugo.

After successfully installing `hugo`, you should see a similar output when running `hugo version`:

```
Hugo Static Site Generator v0.25.1 linux/amd64 BuildDate: 2017-08-03T15:06:42+07:00
```

#### Creating a new site

Now we can use `hugo` to generate our new site. Run

```
hugo new site .
```

to create a new Hugo site in your current repository folder. After running the above command, your folder structure now should be something like:

```
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes

6 directories, 2 files
```

### Creating your first post

To write your first post, simply run:

```
hugo new posts/<post-file-name>.md
```

For example, to create a post called *My First Post*, I would run `hugo new posts/my-first-post.md`

Now, have you seen where the generated file went? That's right, it's in your `/content/posts` folder. The `/content/posts` folder is where Hugo will store all your blog posts. All posts are written in the beautiful **Markdown** format, and a Hugo theme will beautify that format even more. Now, go ahead and write something creative in your markdown file.

Also, notice in your markdown file, the header

```markdown
---
title: "My First Post"
date: 2018-01-07T07:53:25+07:00
draft: true
---
```

This is also used by Hugo to determine when the post was first created, the title of the post and whether the post is a draft or a finished work. To make your post ready to publish, simply remove the line `draft: true`.

### Add a cool theme

After creating our first post, we are ready to add a theme to our Hugo site. We'll use the *temple* theme to get started, however you can of course change the theme after completing this tutorial.

Let's download the Hugo *temple* theme [here](https://github.com/aos/temple). Do **not** clone the repo - simply download it as a zip file (this will prevent git confusions later on).

<img src="/img/downloading_temple_theme.png" align="center" alt="Downloading the temple theme"/>

Now, extract that zip file specifically to your `themes/` folder. Next, rename the folder from `temple-master` to just `temple`.

### Running your site in a local server

After adding a theme to your site, you can run `hugo` on a local server with draft posts enabled:

```
hugo server -D
```

Go to [localhost:1313](http://localhost:1313) to see your awesome new site.

#### Edit that conf.toml!

To customize the theme, and to specify information regarding your blog site, you should edit the `conf.toml` file in root directory. To get started, add these attributes and save the file:

```
baseURL = "https://<github-username>.github.io/"
languageCode = "en-us"
title = "My New Hugo Site"
theme = "temple"
```

If you have a domain ready, be sure to update `baseURL`. Set `theme` to the theme you want to use. Make sure they are downloaded in your `themes` folder though.

### Push to GitHub

Let's commit to our remote GitHub repo. From root directory, run:

```git
git add .
```

```git
git commit -am "Launch Hugo site"
```

```git
git push -u origin develop
```

>We will be working in the *develop* branch. This is so that the site generated by Travis CI later on will go to our *master* branch, and that the default GitHub pages branch is at *master*. The GitHub pages branch cannot be changed for personal websites such as our blog site. Sad face.

Now, all Hugo generated files and our first post should be up in the remote repository. But how do we see our site online? How do you build a site in a remote repository? This is where Travis CI comes in.

## 2. Use Travis to deploy to GitHub pages

Next, we want to use Travis CI to build our blog site with `hugo` and then continuously deploying the site to our GitHub pages space.

First, we will need a Personal Access Token. This will be used by Travis to be able to have write access to our repository, enabling it to deploy our built blog site on another *branch*.

Go to [this link](https://github.com/settings/tokens/new) to create a new Personal Access Token. Next, fill the Token description and tick the **repo** box:

<img src="/img/creating_new_pat.png" align="center" alt="Creating a new Personal Access Token"/>

That is all the access Travis needs! Then, click on **Generate Token** at the bottom. Now, note down the generated token, as we will be using it soon!.

Now, go to [travis-ci.org](http://travis-ci.org/) and login with your GitHub account. Next, click on your profile picture at the top right corner. In the list of repos that you own, choose your blog repo, and flick the switch to turn Travis CI on for that repo.

<img src="/img/travis_activate_blog_repo.png" align="center" alt="Activating Travis to blog site"/>

Next, click on the repo to view its build details (there are no builds yet! We will do this later on). Now go to the **Settings** tab, and scroll to the **Environment Variables**. We will create a new environment variable named `GITHUB_TOKEN` to store our newly created Personal Access Token. For the variable value, just input the generated token that you created earlier. When finished, click **Add** at the bottom to add your environment variable. Now, Travis is capable of rewriting your entire blog repo at your will! (Eek, that sounds scarier than reality)

<img src="/img/creating_env_variable.png" align="center" alt="Creating GITHUB_TOKEN environment variable"/>

#### Creating .travis.yml

After setting up an environment variable on Travis for our repo, we will need to create a .travis.yml to build our blog site using Hugo. You can use the `touch` command to quickly create `.travis.yml`in the root directory:

```
touch .travis.yml
```

First, specify a language. However this will only be used to install and run the `hugo` command. I will use `go` to install `hugo`, but you can use `apt` if you wish:

```yml
language: go
```

Then, I setup Travis to be able to run `hugo` by installing `hugo` in the `install` part:

```yml
install: go get -v github.com/gohugoio/hugo
```

Now, run `hugo` in the `script` part:

```yml
script: hugo
```

Next, the most important part, the `deploy` section. Here Travis will put / deploy the built static website in a separate branch in your repo. You should set the target_branch to be `master` as GitHub pages can only run in the `master` branch:

```yml
deploy:
  provider: pages
  skip_cleanup: true
  github_token: $GITHUB_TOKEN
  local_dir: public
  target_branch: master
  on:
    branch: develop
```

The full `.travis.yml` script:

```yml
language: go

branches:
  only:
    - develop

install: go get -v github.com/gohugoio/hugo

script: hugo

deploy:
  provider: pages
  skip_cleanup: true
  github_token: $GITHUB_TOKEN
  local_dir: docs
  target_branch: master
  on:
    branch: develop
```

#### Push and Voila

Once you have created your `.travis.yml`, simply commit your changes to GitHub.

```git
git add .
```

```git
git commit -am "Build my site with Travis"
```

```git
git push
```

If all goes well, go to [Travis](https://travis-ci.org/), select the blog repo, then watch as Travis automatically build your website. After Travis turns green, go to

```html
<github-username>.github.io
```

to see your new published site.

<img src="/img/green_travis_build.png" align="center" alt="Blog site continuously deployed with Travis"/>

>To learn more about GitHub pages deployment on Travis, see [this link](https://docs.travis-ci.com/user/deployment/pages/).

### Das End

Phew, good job!

From this tutorial, you have managed to use a static website builder, created a blog site with an awesome theme and then integrated a CI service to build your blog site in GitHub pages online. Hopefully, you have learned many useful features of GitHub pages and the power of a static webstite builder such as Hugo. Now, take the next steps to be a blogger by adding more content and customizing your site!
