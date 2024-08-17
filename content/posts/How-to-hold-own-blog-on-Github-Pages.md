+++
title = 'How to Hold Own Blog on Github Pages'
date = 2024-08-17T15:18:43+08:00
draft = false
+++

It is specially written for blogging beginners, aiming to guide you on how to easily set up and host your personal blog on GitHub Pages. for example, if you have isencher account of Github.com, you will get a blog web whose address is https://isencher.github.io.<br>
I use Hugo, a feature-rich static site generator that automatically creates web pages for your blog content. Whenever you update your blog, just run Hugo, and it will quickly generate the latest web pages, ensuring that your website is always up to date.

## Contents
- [Prerequsites](##Prerequsites)
- [Operation Steps](##OperationSteps)

## Prerequsites
- to register a [Github account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home)
- some tools
    - [git](https://git-scm.com) : version control system
    - [gh](https://cli.github.com) : Github cli
    - [hugo](https://gohugo.io/) : automatic generate static web

## OperationSteps
 - 1 create **isencher.github.io** repo
    - 1.1 create local repo
    - 1.2 create the match remote repo and sync
    - 1.3 delete local repo
    - 1.4 Link the repository to https://isencher.github.io
 - 2 create **blog** repo 
    - 2.1 create local repo with hugo
    - 2.2 add submodule ananke theme
    - 2.3 add submodule public
    - 2.4 config blog site
    - 2.5 create blog remote repo and sync
- 3 create a new blog

### 1. create isencher.github.io repo

#### 1.1 create local repo
Open terminal, switch to special floder, eg. d:\isencher, and perform follow command:
```
mkdir isencher.github.io
cd isencher.github.io
```
Create README.md 
```
echo "# isencher.github.io" > README.md
```
init it to become isencher.github.io local repo
```
git init
git add .
git commit -m "Initial commit"
```

#### 1.2 create the match remote repo and sync
```
gh repo create isencher.github.io --public --source=. --push
```
#### 1.3 delete local repo
```
cd ..
rm isencher.github.io -force
```
when meet confirmation, answer a(all).

#### 1.4 Link the repository to https://isencher.github.io
browse https://github.com/isencher/isencher.github.io and click **Settings**, select **Pages** on side bar, select "Deploy from a branch" from **Source**'s dropdown menu, and select "master" and "/(root)" in **Branch** section, the click nearby **Save**.
after above operation, the https://isencher.github.io web is live.

### 2 create blog local repo with hugo

#### 2.1 create local repo
in the same terminal, perform
```
hugo new site blog
```

Next, switch to blog floder, which will become blog local repo
```
cd blog
```

Init it, and become the blog local repo
```
git init
git add .
git commit -m "Initial commit"
```

#### 2.2 add submodule ananke theme
```
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
git commit -m "Add submodule themes/ananke"
```

#### 2.3 add submodule public
```
git submodule add https://github.com/isencher/isencher.github.io.git public
git commit -m "Add submodule public"
```
#### 2.4 config blog site
edit hogo.toml content as following 
```
baseURL = 'https://isencher.github.io/'
languageCode = 'en-us'
title = 'iSencher'
theme = 'ananke'
```
and commit the change
```
git add hugo.toml
git commit -m "Configure site"
```

#### 2.5 create blog remote repo and sync
```
gh repo create blog --public --source=. --push
```

### 3 create a new blog

first create a blog by hugo template
```
hugo new content content/posts/How-to-hold-own-blog-on-Github-Pages.md
```
second, edit the blog by your mind

third, preview by
```
hugo server -D
```

fourth, finalize the draft, set 'draft' to false in the file 'How-to-hold-own-blog-on-Github-Pages.md'.
```
draft = false
```

fifth, regenerate the blog
```
hugo
```

sixth, update public repo
```
cd public
git add .
git commit -m "Add a blog of how to hold own blog on github pages"
git push
```

seventh, update blog repo
```
cd ..
git add .
git commit -m "Add a blog of how to hold own blog on github pages"
git push
```

then, if you reopen https://isencher.github.io, you can see the new blog.






