# Leiden DDE Guidelines

## Structure of the Repository

To bake a cake, one applies a recipe to ingredients (so to speak). In the same way, the website is constructed by applying a set of website-generation instructions (formatting, page structure, etc) to content (the Guidelines). Finally, the cake must be delivered to the customer. Similarly, the website is deployed through Netlify. To facilitate orientation, this is a brief classification and explanation of each of the files in the repository.

### Recipe

The website is produced by Jekyll, a static site generator. Jekyll takes the content files, applies formatting and design, and outputs web-readable files (HTML and CSS files).
- `Gemfile`: Jekyll is written in a programming language called Ruby. Ruby packages software programmes as 'gems'. The Gemfile is a list of gems involved in the production of the website. The gems include Jekyll itself, the theme (just-the-docs), and other plugins which help functionality.
- `Gemfile.lock`: This records the versions of the gems used.

As alluded to above, Jekyll applies a theme - just-the-docs - to the content. More information about the theme is available at the [theme website](https://pmarsceill.github.io/just-the-docs/). FYI: The underscore at the start of the file or folder tell Jekyll that these aren't part of the content (the Gemfiles are special and don't need the leading underscore).
- `_config.yml`: Defines basic parameters used in the theme.
- `_sass`: Defines custom formatting, such as the theme colour.

To facilitate maintenance and avoid the need for editing in Markdown directly, the website can be updated through the Forestry.io content management system (CMS). The CMS pulls content from this repository, then pushes it back once the content has been changed, thus updating the website. Its configuration files are stored in `.forestry`.

### Ingredients

The most important content files are in the `guidelines` folder. Each DDE category has its own file.

There are also a number of other supplementary content files and folders:
- `index.md`: The homepage of the website.
- `downloads.md`: The page where document downloads are available.
- `assets`: The folder where the downloadable files are stored.
- `404.html`: Directs users back to homepage if things go wrong.
- `favicon.ico`: To display the KGF logo in the browser tab.

Finally, the repository comes with this `readme.md` file you're reading now. It's not part of the website, but (hopefully!) helps with navigating the files and folders here.

### Delivery

Netlify reads the recipe and takes the ingredients to bake the cake (build the website) and then delivers it (deploys the website). This happens automatically every time an update is pushed to the repository. Netlify settings are managed separately on the [Netlify website](https://app.netlify.com/) and not through the repository.

## Notes for Content Editors

### Front Matter

Each content page starts with a set of parameters which provide Jekyll with additional information about it. These parameters must be at the beginning, or front, of each page, so they are called front matter. This is the front matter used in the Guidelines pages:
```
---
layout: default
title: A Videos
permalink: /guidelines/a-videos
parent: Guidelines
nav_order: 1
---
```

Some additional details:
- layout: The website is simple and text-based, so the default layout is used. In more complex websites, different layouts may be helpful. For example, an online shop might have a specific page layout for product pages.
- permalink: This sets the hyperlink for the webpage.
- parent: The DDE categories are 'children' of the 'parent' Guidelines section. FYI: In the front matter of the parent Guidelines section, this line is replaced with `has_children: true`!
- nav_order: The pages will be arranged in the sidebar accordance to its nav(igation) order.

### Formatting

The content pages are formatted with the help of Markdown. See this [cheat sheet](https://www.markdownguide.org/cheat-sheet/) for a quick introduction to the most frequently used elements.

The most important elements for our purposes are:
- [Headings](https://www.markdownguide.org/basic-syntax/#headings)
- [Emphasis](https://www.markdownguide.org/basic-syntax/#emphasis) (bold/italics)
- [Footnotes](https://www.markdownguide.org/extended-syntax/#footnotes)
- [Links](https://www.markdownguide.org/basic-syntax/#links)

Please apply the following conventions:
- Use Heading 3 (###) for the Guidelines themselves: `### Guideline A1. Videos...`.
- Insert the following syntax in a line immediately after keywords: `{: .label }`. For example:
```
Keywords: relevance, probative value
{: .label }
```
- Italicise sub-headings within the commentary, followed by a full stop: `*Time Limits*. Pursuant to ...`.
- Place all footnotes (citations) at the end of the document.
