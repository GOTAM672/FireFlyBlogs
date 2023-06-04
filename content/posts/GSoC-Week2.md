---
title: "GSoC 2023 [Week 2 Report]: Add “Remote Desktop” page into the system panel"
date: 2023-06-03T19:45:10+05:30
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
<b>Mentor : [Felipe Borges](https://gitlab.gnome.org/felipeborges)</b><br>
<b>Contributor : [Gotam Gorabh](https://gitlab.gnome.org/gautham_x)</b><br>


#### Introduction

Implementing `Remote Desktop` page will allow user to access and control a computer or a desktop environment remotely from another location.
It allows users to connect to a remote computer or server and interact with it as if they were physically present in front of it.

<b>This week I will implement only the GUI of the Remote Desktop Page.</b>

<b><i>Remote Desktop Mockup</i></b>

![](remote-desktop.png)

I will address this [Issue(#2241)](https://gitlab.gnome.org/GNOME/gnome-control-center/-/issues/2241) and implement this [mockup](https://gitlab.gnome.org/Teams/Design/settings-mockups/-/blob/master/remote-desktop/remote-desktop.png) in this project. For more details here is my [Proposal](https://github.com/GOTAM672/GSoC-Gnome-Proposal).

#### Week 1 Goals:

- Add `remote_desktop_row` using `CcListRow` into empty system panel.
- Implement the content page for the `remote_desktop_row` using `AdwLeaflet`.
- Inside the content page Implement the GUI according to the `Remote Desktop` mockup.
- Take feedback from my mentors and design team members for any modification apart from mockups.
- Eliminate errors and wrong coding standards.

#### Progress Made:

- Added `remote_desktop_row` using `CcListRow` into empty system panel.
![](remote-desktop-row.png)
- Implemented the content page for the `remote_desktop_row` using `AdwLeaflet`.
- Implemented the GUI according to the `Remote Desktop` mockup. 


<b><i>Current look of Remote Desktop page:</i></b>

![](remote-desktop-page.png)


#### Deliverables:

To create a Remote Desktop page, I added three files name `cc-system-remote-page.c`, `cc-system-remote-page.h`, and `cc-system-remote-page.ui` inside `system` folder.

![](week2-structure.png)

Also modified `cc-system-panel.c` , `cc-system-panel.ui` , `system.gresource.xml` , and `system/meson.build` files.  

#### Related Merge Request:

- `system: Add 'Remote Desktop' page into the system panel` [!1818](https://gitlab.gnome.org/GNOME/gnome-control-center/-/merge_requests/1818)


<!--#### Issues and Challenges:-->


#### Plan for the Next Week:

In the next week, I will move `About panel` as a page into the new system panel. 

This week is not over yet, so stay tuned for more updates.

<!--#### Questions and Discussion Points:

#### Conclusion:


#### Additional Resources:-->
---

