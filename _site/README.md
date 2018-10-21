# Penn Data Science Group website

## Build site

To build the website locally, clone the repo with:

```
git clone https://github.com/penndsg/website_source.git
```

Make sure you have ruby installed (preferrably using RVM). If you don't have the `bundler` gem installed, install it by typing

```
gem install bundler
```

Then install necessary Ruby dependencies by running `bundle install` from within the `website_source` directory.  After this, the site can be be built with:

```
jekyll build
```

This creates the static website files in the `_site` directory. To view the site, run `jekyll serve` (still from within the `website_source` directory) and point a browser to `http://localhost:4000/`.  More information on Jekyll can be found [here](http://jekyllrb.com/).

## Add new member

To add a new member, use the `new_member.py` script. For example, to add John Doe, type

```
python new_member.py "John Doe"
```

This will create a file with a path like `members/_posts/2016-12-14-john-doe.md`. The file will look something like this:

```
---
layout: member
title: "John Doe"
degree: "[Degree] [Program] [Grad Year]"
# cv: /pdfs/members/john-doe-cv.pdf
# resume: /pdfs/members/john-doe-resume.pdf
# twitter: your-twitter-handle
# github: your-github-handle
# bitbucket: your-bitbucket-handle
# scholar: your-google-scholar-id
# linkedin: your-linkedin-id (the part that goes after linkedin.com/in/)
# researchgate: your-researchgate-id
# website: your-website.com
# email: name at example.edu
# phone: "(123) 456-7890"
# image: /images/members/john-doe.jpg
---

Tell us about yourself here. You can add links like [this](https://www.google.com/search?q=this).
```

Open this file and edit it to your liking. Add info for whatever links you want to appear in your profile and uncommend those lines. Feel free to delete commented lines you don't want to use. If you don't want a boring default profile picture, add a SQUARE profile picture (same number of pixels wide as tall) to (in this case) `/images/members/john-doe.jpg` and uncomment the image line.

## Add new blog post

To add a new blog post, type

```
python new_blog_post.py "My Blog Post Title"
```

This will create a file with a path like `projects/_posts/2018-09-26-my-blog-post-title.md`. This file will look something like this:

```
---
layout: post
title: "My Blog Post Title"
# author:
# image: /images/blog/my-blog-post-title.png
---

Blog post content here. To see what you can do with Markdown, check out
[this Markdown cheatsheet]
(https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
```

Uncomment the `author` line and add the name of the author. If the name matches
the name of someone with a member profile (someone with a file in
`members/_posts/`), then their image will be displayed over their name in the
blog post, and a link to their profile will be generated.

If there's a header image associated with the blog post, uncomment the `image`
line in the file and make sure the path points to a valid image.

## Add a new event

For that, just copy a previous event file in the `events/_posts` directory. Make sure the date in the file name is the date of the event. Edit the file to your liking. Make sure to add a picture associated with the event and uncomment the image line.

## Commit and push changes to the source files

If you have write access to this git repo (website admins only), then after you make changes locally you'd like the website to have, do a `git add .`, `git commit -m "commit message"`, and `git push origin master` from within the `website_source` directory. This does not save the generated source files since `_site` is included in the `.gitignore` file.

If you don't have write access, then fork this repo and create a pull request after you push your changes to your own repo. We'll review the changes and either accept them or work with you to clean them up.

## Deploy site (website admins only)

To deploy changes to the site, first make sure you have been added as a contributor to the penndsg/website_source.git repo, then type

```
./deploy.sh
```

from within the `website_source` directory. You should immediately see your changes reflected in penndsg.github.io.
