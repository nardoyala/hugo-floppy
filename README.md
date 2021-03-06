# Floppy
...is a blog theme that is inspired by [Tania Rascia's](https://github.com/taniarascia) website ([version 4.0](https://www.taniarascia.com/website-redesign-version-4-0/)). I forked the base of this project from [Hugo-Vitae](https://github.com/dataCobra/hugo-vitae/)

## Demo

On https://themes.gohugo.io you can look up a demo.
[Link to demo](https://bernardoayala.com)

![Screenshot](https://github.com/nardoyala/hugo-floppy/blob/main/images/screenshot.png)

## Features

* Easy to use, even with GDPR in mind
* Optimized responsiveness for all kinds of devices
* Multilingual support for fixed strings
* Choose every free FontAwesome icon for the social navbar
* FontAwesome, RobotoMono and Lato as local used fonts
* Third party services can be completely turned off
* Name the taxonomies as you like
* Multiple taxonomies work flawless with single post
* New list of all taxonomies and tags below the post in single view
* New array front matter notaxonomy
* Author/Writer display in post with extra features
* New bool front matter nofeed
* Multilingual support for month names
* Syntax highlighting
* Custom CSS
* RSS feeds
* Twitter cards and opengraph tags integration

For more explanation about some features, scroll down
to **Features**

## Installation

Change your current work directory into the root directory of your hugo site
and clone the repository:

```sh
cd themes
git clone https://github.com/nardoyala/hugo-floppy.git hugo-floppy
```

For more information about installation read the
[official setup guide](https://gohugo.io/overview/installing/) of Hugo.

## Features

### GDPR in mind

The GDPR has many rules for third party assets, so if you don't want to think
about GDPR complaints you can disable every third party asset that is
integrated.

Some websites using webfonts from third party sites like google. This theme
brings FontAwesome and Roboto(-Slab) directly with it without having to
integrate them via third party sites.

### Setting the month names in another language

Due to the currently unavailable feature for multilingual dates in `.Date`
from Go. It is possible to create a `month.yaml` in the data folder of your
Hugo site root directory. There is also an example file in
`exampleSite/data/`.

```sh
cat > month.yaml << EOF
1: "Jan"
2: "Feb"
3: "Mar"
4: "Apr"
5: "May"
6: "Jun"
7: "Jul"
8: "Aug"
9: "Sep"
10: "Oct"
11: "Nov"
12: "Dec"
EOF
```

### Setting the language for the fixed strings

There are some fixed strings in the html files that normally uses only the set
language. But if you create a folder `i18n/` in the root directory of your
hugo site and copy the `en.yaml` that comes with the theme you can edit the
fixed strings to your liking. Don't forget to also set
`defaultContentLanguage = "en"` to the new language.

```sh
mkdir i18n
cd i18n
cp ../themes/hugo-floppy/i18n/en.yaml en.yaml
# Edit the new language file
```

### FontAwesome for social icons

FontAwesome is mainly used for the icons of the social navbar in the top right
corner of the theme. In the config of your hugo website there is a param
called `icon` for the `params.social` section. I could look like this:

```toml
[[params.social]]
name = "Github"
icon = "fab fa-github"
url = "https://github.com/nardoyala/hugo-floppy"
```

On the [FontAwesome](https://fontawesome.com) website, you can look up every
free icon and also the information you need to put into this `icon` param.

### Content type

You can specify content type with field `type` in your content. For example
static pages can be set as type `page` which are excluded from recent posts,
lists and they don't show there taxonomies below the page. You can use site
params `mainSections` and `disableDisqusTypes` to control which page types
are excluded from recent posts and Disqus comments respectively.

```md
---
title: "About"
date: 2019-04-19T21:37:58+05:30
type: "page"
---

This is some static page where you can write about yourself.
```

### Taxonomies and tags

Since the release of version 1.0.2 it is possible to name the keywords and
taxonomies freely and therefore be much more flexible. Especially if you use
the theme with a language other than English. Also, the different taxonomies
will now be displayed below the post.

Here is an example of different taxonomies in the config file:
```toml
[taxonomies]
  tag = "tags"
  series = "series"
  author = "authors"
```

If you use one or more of these taxonomies in your posts there will be
displayed in a new list below the content of the post.

#### Front matter "notaxonomy" for taxonomies

Since release 1.0.2 Vitae shows every taxonomy a post is part of below the
content. This could lead to a very unpleasantly large number of taxonomies
under the post.

With the new front matter `notaxanomy` you can specify every taxonomy that
should **not be visible** below the content. You can also use the type page
as explained at **Content type** to disable the taxonomie view completely.

```md
+++
title = "spf13-vim 3.0 release and new website"
date = "2012-04-06"
description = "spf13-vim is a cross platform distribution of vim plugins and resources for Vim."
tags = [".vimrc", "plugins", "spf13-vim", "vim"]
series = ["learn vim","vim2.0"]
authors = ["John Doe","Jane Doe"]
notaxonomy = ["series","authors"]
+++
```

In the example above the post does only show the "tags" below the content.

### Display for author/writer

The author/writer can now be displayed on the content page. To activate the
function, the option `listAuthor` must be set to `true` in the config.

If you consider to give a link to the author, just use the new front matter
`authorlink`. This option creates a link on the author name to the selected
website.

All content that has no author set, will not use this feature obviously.

### Front matter "nofeed" for RSS

If you have pages, posts or other content that should not show up in the RSS
feed of your website. You can set the new front matter `nofeed` for this
content. It's a boolean, you could use either `true` or `false`.

If you want to modify the `index.xml` layout. Copy the Floppy layout from
`hugo-floppy/layouts/index.xml` to your Hugo site root directory into the
folder `layouts/` and change it the way you want.

## Credits

* [hugo-vitae](https://github.com/dataCobra/hugo-vitae/) from which Floppy was forked
* [freepik](https://www.freepik.com) for the avatar
* [icons8](https://icons8.com/) for all the icons
* [google](https://fonts.google.com) for the roboto and lato fonts
* [fontawesome](https://fontawesome.com) for providing amazing icons

Licensed under the [GPL-2.0](https://raw.githubusercontent.com/nardoyala/hugo-floppy/main/LICENSE.md).
