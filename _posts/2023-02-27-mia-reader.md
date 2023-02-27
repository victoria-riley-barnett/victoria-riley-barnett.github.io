---
layout: posts
title:  "mia-reader"
date:   2023-02-27 02:03:50 -0700
tags: Projects Programming
---

# A marxist internet archive reading mirror

![2023-02-27_01-28](https://user-images.githubusercontent.com/9009959/221525776-f597e8fe-565d-4ffb-8405-554232ac434a.png)

### Links
- [Github](https://github.com/victoria-riley-barnett/mia-reader)
- [Marxist Internet Archive](https://www.marxists.org/)


## Introduction
One of the only bad things about free internet archives is that they usually exist in the state they were uploaded in. In the case of the Marxist Internet Archive, this is doubly true - not only does it use really ugly html for most of its pages, the format and css created for those pages is not consistent and is in most cases difficult to read. The standard use-case for the archvie as such then, as I've seen it used amongst reading groups and other users, is to either copy all of the text from a given archive page and rehost it on Google docs for collaborative commenting, or to download the provided pdf/epub/mobi files and read them on a device. The goal of mia-reader is to provide a free mirror of Marxist Internet Archive content that is easy to read and navigate regardless of device, can automatically export to Google docs, and can generate pdf/epub/mobi files for offline reading on demand.

## Launch
To launch, I'm starting with a mirror of both the Selected Marxists section and the Marx-Engels-Lenin section of the archive, two of the most popular sections of the archive. As I don't have official mirror status with mia to use rsync and Apache to mirror the site, all mirror sections are manually generated using a combination of ```wget```, ```find```, ```sed```, ```pandoc```, and good old manual editing.

## The Process
So far, my process for generating each section is as follows:
- Download the html for the section using ```wget -mpE -w .5 --limit-rate=500k -r --level=2  https://www.marxists.org/archive/your-category-here (initial section was: arvhive/marx/works/sw/progress-publishers/one-volume.htm)```
- Use ```find``` and ```pandoc``` to convert all html files to markdown files using ```find ./ -iname "*.htm" -type f -exec sh -c 'pandoc "${0}" -o "${0%.*}.md"' {} \;```
- Use ```bash``` and ```sed``` to insert Jekyll front matter into all .md files
- Use ```find``` again to remove all .htm files using ```find . -type f -iname "*.html" -delete```
- Manually lint files for errors, readability, and consistency
- Manually edit files to add links to other files in the archive
- Manually edit files to add proper jekyll nav structure to front matter

## The tools
- [Jekyll](https://jekyllrb.com/) - Jekyll is a static site generator that uses markdown files to generate html pages. While static-content generators don't fit every use-case, they are great for sites like mia-reader that don't need to be updated frequently, and markdown is the perfect format to use for both web hosting and generating other file types from. Jekyll is free and I also use it for this blog!
- [Pandoc](https://pandoc.org/) - Pandoc is a great tool for converting between file formats. I use it to convert html to markdown, but it can also convert between many other formats, including pdf, epub, and mobi, html, docx, LaTeX, and many more.
- [Just-the-docs](https://github.com/just-the-docs/just-the-docs) - Just-the-docs is a Jekyll theme primarily meant for documentation sites, but I think it's navigation structure is perfect for a site like mia-reader. It's also very easy to customize, free to use, has easy gh-pages hosting(though I'm not using it), and is very well documented.
- [Font Awesome](https://fontawesome.com/) - Font Awesome is tool for adding icons to your site. I use it for the search icon and my light/dark mode toggle.
- [wget](https://www.gnu.org/software/wget/) - wget is a great tool for downloading files from the internet. It has a ton of options and has made the process of downloading from the archive much easier.
- [

## The Future
I plan to continue expanding mia-reader. Some of the things I'd like to add are:
- [x] A search function
- [x] Comphrensive contribution guide with the goal of making it easy for anyone to contribute, and getting more sections on mia-reader
- [x] User configurable options for dark mode
- [ ] User configurable options for font size, font type, and line spacing
- [ ] A way to automatically generate a pdf/epub/mobi file for offline reading
- [ ] A way to automatically generate a Google docs file for collaborative reading
    - Google Drive API can do this, but my link structure is not stable enough to use it yet (will need to host on a domain first)
- [ ] Become an official mirror of the archive so I can do much more of this automatically and get new content as it's added to the archive
- [ ] Would love multiple languages but I'm hesitant to add them at the moment, as my linting process is very manual and I couldn't guarantee the quality of the translations after my conversion process.

and finally, as ever:

- [ ] Add more sections of the archive

## Contributing
For more detailed technical information or to get involved, checkout the [contribution guide on Github](https://github.com/victoria-riley-barnett/mia-reader/blob/main/CONTRIBUTING.md). If you have any questions, feel free to open an issue on Github or contact me!

