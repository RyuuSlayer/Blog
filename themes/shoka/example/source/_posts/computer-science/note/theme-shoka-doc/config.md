---
title: Step.2 Basic Configuration
date: 2020/08/13 20:56:48
categories:
- [Computer Science, Binary Miscellany, Theme Shoka Documentation]
tags:
- Hexo
- Tutorials
valine. placeholder: "1:
  placeholder: "1. Please read this documentation carefully before asking questions ⚡\n2. page display problems 💥, please provide a screenshot of the console 📸 or your test URL \n3. any other reported errors 💣, please provide a detailed description and screenshot 📸, good luck! Happy eating 💪"
audio:
  - https://music.163.com/song?id=1387098940
---

:::primary
[:rocket:quickstart](/computer-science/note/theme-shoka-doc/) - [:love_letter:dependency plugin](/computer-science/note/theme-shoka-doc/dependents/) - [* *:pushpin:basic configuration**](/computer-science/note/theme-shoka-doc/config/) - [:rainbow:interface-display](/computer-science/note/theme-shoka-doc/display/) - [:unicorn:special function](/computer-science/note/theme-shoka-doc/special/)
:::


# site aliases
```yml
alternate: Yume Shoka
```
The name set here is displayed at the top of the page instead of the logo, and at the end of the page at :copyright:

# Static file directory
```yml
statics: / #//fastly.jsdelivr.net/gh/amehime/shoka@latest/
```
The default value is `/`, which means use local static files
This can be modified to the form `//fastly.jsdelivr.net/gh/your github username/your project name@latest/` to use jsDelivr for acceleration.
PS: jsDelivr is not updated in real time, so you need to be patient after regenerating the file

```yml
css: css
js: js
images: images
```
The actual directory name of the directory where the static files are located, these are generally not changed.

# night mode
```yml
darkmode: # true
```
By default, whether night mode is enabled or not depends on (from highest to lowest priority)
1. the visitor's own choice by clicking the toggle button in the page header
2. the visitor has switched the theme color of the browsing device
3. your `darkmode` configuration item

# Auto-positioning
```yml
auto_scroll: # false
```
By default, when the page is opened again, it will automatically scroll to the last viewed position.
Setting this option to ``false`` will disable this feature.

# Loading animation
```yml
# Whether to show the page loading animation loading-cat
loader:
  start: true # Show loading animation when the page is opened for the first time
  switch: true # Show loading animation when tab is switched to another page
```

After tab switch, just show loading animation, not actually reload the page

# Page effects
Click on the page of the fireworks effect configuration as follows

```yml
fireworks:
  enable: true # whether to enable
  color: # firework color
    - "rgba(255,182,185,.9)"
    - "rgba(250,227,217,.9)"
    - "rgba(187,222,214,.9)"
    - "rgba(138,198,209,.9)"
```

# Load Google Fonts
```yml
font:
  enable: true
  # Font options:
  # `external: true` will load this font family from `host` above.
  # `family: Times New Roman`. Without any quotes.
  # `size: x.x`. Use `em` as unit. Default: 1 (16px)

  # Global font settings used for all elements inside <body>.
  global:
    external: true
    family: Mulish
    size:

  # Font settings for alternate title.
  logo:
    external: true
    family: Fredericka the Great
    size: 3.5

  # Font settings for site title.
  title:
    external: true
    family: Noto Serif JP
    size: 2.5

  # Font settings for headlines (<h1> to <h6>).
  headings:
    external: true
    family: Noto Serif SC
    size:

  # Font settings for posts.
  posts:
    external: true
    family:

  # Font settings for <code> and code blocks.
  codes:
    external: true
    family: Inconsolata
```

This function is basically referenced to NexT.
The font for bolded headings always uses `Noto Serif`, and the font settings for `headings` and `title` are loaded successively in order to display the Chinese characters in Japanese correctly and friendly.

# `iconfont` icon
The theme doesn't use Font Awesome directly because it feels very wasteful to not use so many icons, so I recreated a project on Iconfont.
`font-family` is set to `ic` and all font styles are prefixed with `i-`, see `<root>/themes/shoka/source/css/_iconfont.styl` for details.

``yml
# project of https://www.iconfont.cn/
# //at.alicdn.com/t/font_1832207_c8i9n1ulxlt.css => 1832207_c8i9n1ulxlt
iconfont: "1832207_c8i9n1ulxlt"
```

If you need to add or modify it, please leave a comment with your [Iconfont](https://www.iconfont.cn/) username and I will add you to the current [project](https://www.iconfont.cn/manage/index?manage_type=) myprojects&projectId=1832207).

Add permission as `read-only`, after that you can select all as many as you want, save them to cart in bulk, add them to your own project, and change the `iconfont` value in the theme profile to your project.

Note that your project should set the `FontClass/Symbol prefix` to `i-`.

Create a new file `iconfont.styl` in the `<root>/source/_data/` directory and copy the new or modified icon styles into this file.

> The custom `iconfont.styl` file will overwrite the theme default style, to avoid errors, please make sure the original style names all exist, add, delete and change on top of the original style.

# Menu and social buttons

```yml
menu:
  home: / || home
  about: /about/ || user
  posts:
    default: / || feather
    archives: /archives/ || list-alt
    categories: /categories/ || th
    tags: /tags/ || tags
  # friends: /friends/ || heart
  # links: /links/ || magic

social:
  github: https://github.com/yourname || github || "#191717"
  #google: https://plus.google.com/yourname || google
  twitter: https://twitter.com/yourname || twitter || "#00aff0"
  zhihu: https://www.zhihu.com/people/yourname || zhihu || "#1e88e5"
  music: https://music.163.com/#/user/home?id=yourid || cloud-music || "#e60026"
  weibo: https://weibo.com/yourname || weibo || "#ea716e"
  about: https://about.me/yourname || address-card || "#3b5998"
  #email: mailto:yourname@mail.com || envelope || "#55acd5"
  #facebook: https://www.facebook.com/yourname || facebook
  #stackoverflow: https://stackoverflow.com/yourname || stack-overflow
  #youtube: https://youtube.com/yourname || youtube
  #instagram: https://instagram.com/yourname || instagram
  #skype: skype:yourname?call|chat || skype
  #douban: https://www.douban.com/people/yourname/ || douban
```
As above, use `||` as a separator, in order `link || icon || color`.
Note that only the icon name needs to be written, e.g. `github`, which will be automatically converted to `ic i-github`.
Hexadecimal color codes need to be `""` wrapped around.

`menu` supports one level of subdirectories, and the first item in the subdirectory settings must be `default`, which is used to define the style of the parent button.

The menu display text can be defined in the language pack, [please poke here for details](. /display/# custom language packs)


# Sidebar configuration

Sidebar can be selected on the left, or on the right
Modify the address of the header file, relative to the path configured in the static file directory `images`.

``yml
sidebar:
  # Sidebar Position.
  position: left
  #position: right
  # Replace the default avatar image and set the url here.
  avatar: avatar.jpg
```

You can put your own images in the `<root>/source/_data/images/` directory, or even overwrite the default avatar image in the theme with the same name, [poke here for details](. /display/# custom theme images)

# Bottom widgets
Currently two widgets can be displayed at the bottom of the page, ``Random Posts`` and ``Recent Comments``.

``yml
widgets:
  random_posts: true # Show random posts
  recent_comments: true # Show recent comments
```

# Word count and reading time statistics

After installing the `hexo-symbols-count-time` plugin, you do not need to modify the site configuration file, just use the default configuration of the plugin directly.

You need to modify the theme configuration file, find two ``cout``s and modify them to ``true``.

```yml
# footer site-wide statistics
footer:
  since: 2010
  count: true

# Article interface statistics
post:
  count: true
```

# Article comments
[How to get the appId and appKey of LeanCloud](https://valine.js.org/quickstart.html).

```yml
valine:
  appId: #Your_appId
  appKey: #Your_appkey
  placeholder: ヽ(○´∀`)ノ♪ # Comment box placeholder
  avatar: mp # Gravatar style : mp, identicon, monsterid, wavatar, robohash, retro
  pageSize: 10 # Pagination size
  lang: zh-CN
  visitor: true # Article visitors statistics
  NoRecordIP: false # No IPs are recorded
  serverURLs: # When the custom domain name is enabled, fill it in here (it will be detected automatically by default, no need to fill in)
  powerMode: true # Turn on comment box effects by default
  tagMeta:
    visitor: new friend
    master: master
    friend: little friend
    investor: golden master poop
  tagColor:
    master: "var(--color-orange)"
    friend: "var(--color-aqua)"
    investor: "var(--color-pink)"
  tagMember:
    master:
      # - hash of master@email.com
      # - hash of master2@email.com
    friend:
      # - hash of friend@email.com
      # - hash of friend2@email.com
    investor:
      # - hash of investor1@email.com
```

The tag tag is displayed after the commenter's name, and the default is the value corresponding to `tagMeta.visitor`.
In `tagMeta` and `tagColor`, except for the key `visitor`, which cannot be modified, all other keys can be changed, but you need to ensure consistency.

```yml Give a chestnut
  tagMeta:
    visitor: visitor
    admin: administrator
    waifu: my wife
  tagColor:
    visitor: "#855194"
    admin: "#a77c59"
    waifu: "#ed6ea0"
  tagMember:
    admin:
      # - hash of admin@email.com
    waifu:
      # - hash of waifu@email.com
```

The above parameters can also be configured in the article Front Matter, which will override the global configuration when accessing the article page.
In particular, it can be used to configure a special placeholder.

```yml
valine:
  placeholder: "1. Please read this document carefully before asking questions ⚡\n2. page display issues 💥, please provide a screenshot of the console 📸 or your test URL \n3. any other reported errors 💣, please provide a detailed description and screenshot 📸, good luck! Happy eating 💪"
---
```

Comment Notification & Management Tool recommends using this [Valine-Admin](https://github.com/DesertsP/Valine-Admin).
Note that `SITE_URL` needs to end with `/`.

If a post needs to have the commenting feature turned off, configure in the post Front Matter that

```yml
---
title: Turn off comments
comment: false
---
```

# Background music
In the theme profile, set the global playlist.
In the article's Front Matter, set the article's proprietary playlist to override the global configuration when visiting that article page.

```yml single list
audio:
  - https://music.163.com/song?id=1387098940
  - https://music.163.com/#/playlist?id=2088001742
  - https://www.xiami.com/collect/250830668
  - https://y.qq.com/n/yqq/playsquare/3535982902.html
```
As above, you can directly use NetEase cloud, shrimp, QQ music playlist, single song, you can fill more than one at the same time.

```yml Multi-list
audio:
  - title: Playlist 1
    list:
      - https://music.163.com/#/playlist?id=2943811283
      - https://music.163.com/#/playlist?id=2297706586
  - title: Playlist 2
    list:
      - https://music.163.com/#/playlist?id=2031842656
```

If custom media files are required, they can be filled out in the following format.

```yml single list
audio:
  - name: "track1"
    url: "play address"
    artist: "artist"
    cover: "cover"
    lrc: "lyrics"
  - name: "track 2"
    url: "play address"
    artist: "artist"
    cover: "cover"
    lrc: "lyrics"
```

```yml multi-list
audio:
    - title: list1
      list:
        - name: "track1"
          url: "play address"
          artist: "artist"
          cover: "cover"
          lrc: "lyrics"
        - name: "track 2"
          url: "play address"
          artist: "artist"
          cover: "cover"
          lrc: "lyrics"
    - title: list2
      list:
        - https://music.163.com/#/playlist?id=2031842656
```

To disable the background music player for the current page, configure in the article Front Matter.

```yml
---
title: Turn off background music
audio: false
---
```

# Random Gallery
- The default list of images is located in `<root>/themes/shoka/_images.yml`.
  Used the Jagged Wave Gallery, using some upload tools like [here](https://pic.gimhoy.com/)
  The link to the image after upload is `https://ryuum3gum1n.de/assets/bg/6833939bly1gicmnywqgpj20zk0m8dwx.jpg`.
  Just write `- 6833939bly1gicmnywqgpj20zk0m8dwx.jpg` on a new line.

  If you want to customize it, create a new `images.yml` file in the `<root>/source/_data/` directory with at least 6 images, which will completely override the default image list

- You can also write any accidental chain image address directly in the image list yml file
```yml
- https://i.loli.net/2020/10/30/qAMYEFXxJcKRsiG.gif
- https://i.loli.net/2020/10/30/rjdhcSgEN8COBPA.jpg
- https://i.loli.net/2020/10/30/HKyzSd7NI3mlBpt.jpg
- https://i.loli.net/2020/10/30/Y1CBXqgeokEs457.jpg
- https://i.loli.net/2020/10/30/Z5W6r2BSoiThHG1.jpg
```

- It is also possible to set up the graph bed API in the theme configuration file at
```yml example
image_server: "https://ryuum3gum1n.de/"
```

# Loading third-party components
```yml
vendors:
  css:
    # ...
  js:
    # ...
```
包括

--|--|--
`pace` | load progress bar|global
`pjax` | page load without refresh|global
`anime` | js animation effects|global
`algolia` `instantsearch`| algolia-based site search|global
`lazyload` | image lazyload|global
`quicklink` | link resource preload|global
`fetch` | get playlist|global
`katex` `copy_tex`|math formula display and copy|on demand
`fancybox` | Image Enlargement and Alignment|On Demand
`valine` | LeanCloud-based commenting system and article reading statistics|on demand
`chart` | Chart Display|On Demand

The above file loading is all based on jsDelivr, with file merging of globally loaded components.
If you don't understand what it means, then don't modify it easily.

:::danger
This may be modified when the theme version is upgraded.
If you have modified the theme default `_config.yml`, remember to update the theme with `vendors` at the end as well.
:::