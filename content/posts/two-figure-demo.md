---
title: Two Figure Demo
date: 2024-01-01
lastmod: 2025-07-19T08:05:59-05:00
# author: Gregg Claycamp
# avatar: /img/author.jpg
# authorlink: https://author.site
# cover: /img/cover.jpg
# images:
#   - /img/cover.jpg
categories:
  - documentation
  - shortcodes
tags:
  - figures
  - 
nolastmod: true
math: true
draft: true
weight: 998
---

A simple way to have side-by-side rendered figures using `HUGO`'s embedded `figure` shortcode. 

<!--more-->

### The shortcode 

Copy the shortcode `two-figures.html` template to your `/layouts/shortcodes/` folder.
 
### In your markdown file, enter two figure shortcodes

Note that the "start/end two figures" before and after the `{{</* figure */>}}` call are optional comments for your use. Text between the comment tags e.g, \<!--_your comment_--\>,  will not appear in the rendered page. 


```go {copy="true"} 
<!--start two figures-->
<!-- First, the shortcode call for the two-figure block -->

{{</* two-figures */>}}

{{</* figure
  src="images/Gregg-Rebecca-Obidos.JPEG"
  link= <optional>
  alt="Happy Travelers"
  caption="Óbidos is a picturesque medieval 
  town known for its tourists, including 
  these happy travelers."
  class="column" 
  width="100%"
  */>}}

{{</* figure
  src="images/Obidos-castle-Randy.jpg"
  link= <optional>
  alt="Obidos Castle"
  caption="Another view of Óbidos Castle 
  (Courtesy of Randy Feldman). The castle
  is often believed to have appeared in 
  Game of Thrones due to its similarity to 
  a particularly photogenic Spanish castle."
  class="column" 
  width="100%"
  */>}}
 
<!--Add the closing tag for the two-figure block -->
{{</* /two-figures */>}}

<!--end two figures-->
  ```

**class=** "column" is a css class that will be applied to the figure. The class is defined in the custom.css file. The class="column" is used to make the two figures appear side by side.

**link=** <optional> is a link to the image file. If you do not specify a link, the image will not be clickable. If you do specify a link, the image will be clickable and will open in a new tab. Leave **link=** off the list entirely or **link=""** if you don't want the image to be clickable.

**caption**= <optional> is a caption for the image. If you  specify a caption, the caption will appear below the image.

**width=**  is the width of the image. The **width="100%"** is used so that the image will fill the column.


### Shortcode syntax

The shortcode tag syntax is critical: `HUGO` uses double curly braces from the `GO` language and the `<>` pair to assign a shortcode. The shortcode is given by `{{</* shortcode-name */>}}` when the shortcode is self-closing,  `{{</* shortcode-name */>}}...{{</* /shortcode-name */>}}` if there is an opening and closing tag. 

### Image source  
The `{{</* figure */>}}` shortcode `src=` argument is a file path relative to your leaf bundle. For example,
a content directory can hold image resources adjacent to the markdown file, such as the Madrid bundle in the following code box. An alternative is to place a post's image resources in a subfolder, as is shown for the Lisbon bundle. (Recall that a _index.md file at the content or posts level is a listing template to show all of the posts in the content or other folder.)

```go 
posts/
├── Madrid/
│   ├── index.md
│   ├── image-1.jpg
│   └── image-2.png
├── Lisbon/
│   ├── images/
│   │   └── image-1.jpg
|   |   └── image-2.jpg
│   └── index.md
└── _index.md


Calling the figure shortcode:
For Madrid images, src="image-1.jpg".
For Lisbon images, src="images/image-1.jpg.
If the image in the /static/img/ folder, use
src="/img/image-1.jpg
```

### Right-to-left order
Note that the two figure calls in the above code box and in your markdown file are in the left-to-right order that you expect them to appear.  

## Two Figures Demo


{{< two-figures >}}
{{< figure
  class="column"
  src="/img/Gregg-Rebecca-Obidos.JPEG"
  link="/img/Gregg-Rebecca-Obidos.JPEG"
  alt="Happy Travelers"
  caption="Óbidos is a picturesque medieval town known for its tourists, including these happy travelers."
  width="100%"

>}}
{{< figure
  class="column"
  src="/img/Obidos-castle-Randy.jpg"
  link="/img/Obidos-castle-Randy.jpg"
  alt="Obidos Castle"
  caption="Another view of Óbidos Castle (Courtesy of Randy Feldman). The castle is often believed to appear in Game of Thrones due to its similarity to a particularly photogenic Spanish castle."
  width="100%" 
  >}}
  {{< /two-figures >}}
<!--end two figures-->

### A bit of following text

This paragraph is added to expose any `css` styling conflicts that might occur after adding new css styles to the existing theme styles. During testing, some following text overlapped the `Previous` and `Next` buttons.

