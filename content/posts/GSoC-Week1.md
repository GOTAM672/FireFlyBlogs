---
title: "GSoC 2023 [Week 1 Report]: Create a New “System” panel in GNOME Settings"
date: 2023-05-26T20:44:02+05:30
draft: false

authors: []
description: ""
license: ""
images: []

tags: []
categories: []
series: []
series_weight: 1


seriesNavigation: true
featuredImage: "gnome_gsoc.png"
featuredImagePreview: "gnome_gsoc.png"

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
linkToSource: false
linkToEdit: false
linkToReport: false
rssFullText: true
license: ''

toc:
  enable: true
  auto: true
code:
  copy: true
  # ...
table:
  sort: true
  # ...
math:
  enable: true
  # ...
mapbox:
  accessToken: ""
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
outdatedArticleReminder:
  enable: false
  # ...
sponsor:
  enable: false
  # ...
related:
  enable: false
  count: 5



---

<b>Project Title : Create a New “System” panel in GNOME Settings</b><br>
<b>Mentor : Felipe Borges</b><br>
<b>Contributor : Gotam Gorabh</b><br>


#### Introduction

This summer I'm working on a project titled Create a New "System" panel in GNOME Settings, which aims to create a New System panel. This blog summarizes my progress during the bonding period and the first week of the Google Summer Of Code 2023.

I will address this [Issue(#2241)](https://gitlab.gnome.org/GNOME/gnome-control-center/-/issues/2241) and implement this [mockup](https://gitlab.gnome.org/Teams/Design/settings-mockups/-/blob/master/system/system-panel.png) in this project. For more details here is my [Proposal](https://github.com/GOTAM672/GSoC-Gnome-Proposal).

#### Week 1 Goals:

- Add an empty system panel to the panel list of GNOME Settings.
- Eliminate errors and wrong coding standards.

#### Progress Made:

- Completed the setup of the development environment and configured the project structure.
- Gathered all the necessary documents that will help in this project such as <b>GObject, GTK</b>, etc.
- Took inspiration from other panels(especially the <b>Accessibility panel</b>) to implement a new system panel. 
- Successfully implemented a new empty system panel.

<b><i>Current status of system panel:</i></b>

![](week1.png)


#### Deliverables:

To create a new system panel, I created a new folder name `system` inside `gnome-control-center/panels` folder.  
Below is the structure of the files and folders inside `system` folder  

![](structure.png)

- `gnome-system-panel.desktop.in` is a new desktop file for the system panel which needs to be installed into the system path to load the panel
- `org.gnome.Settings-gear-symbolic.svg` file provides a gear symbolic icon to the new system panel.

Also modified `gnome-control-center/panels/meson.build` , `gnome-control-center/shell/cc-panel-list.c` , and `gnome-control-center/shell/cc-panel-loader.c` files.  

For more detail, Please see my Merge Request [https://gitlab.gnome.org/GNOME/gnome-control-center/-/merge_requests/1800](https://gitlab.gnome.org/GNOME/gnome-control-center/-/merge_requests/1800).


<!--#### Issues and Challenges:-->


#### Plan for the Next Week:

In the next week, I will move `Region & Language Panel` as a page into the new system panel. 

This week is not over yet, so stay tuned for more updates.

<!--#### Questions and Discussion Points:

#### Conclusion:


#### Additional Resources:-->
