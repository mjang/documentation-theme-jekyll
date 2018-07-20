# ForgeRock EA Documentation

This is the Early Access developer docs site for the ForgeRock Idenity Cloud. Site: https://forgecloud.github.io/


## Setup

Site built with [Jekyll](http://jekyllrb.com/) version 3.3.1, but should support newer versions as well.

Install the dependencies with [Bundler](http://bundler.io/):

~~~bash
$ bundle install
~~~

Run `jekyll` commands through Bundler to ensure you're using the right versions:

~~~bash
$ bundle exec jekyll serve
~~~

### Learn about Jekyll

* Learn Jekyll with step-by-step tutorials and videos at [Jekyll Tips](http://jekyll.tips/).
* Jekyll cheat sheet [Jekyll Cheat Sheet](https://learn.cloudcannon.com/jekyll-cheat-sheet/).

### Documentation pages

* Add, update or remove a documentation page in the *Documentation* collection.
* Change the category of a documentation page to move it to another section in the navigation.
* /samples folder contains some examples of urls, links and formatting
* Documentation pages are organized in the navigation by category, with URLs based on the path inside the `_docs` folder.

### Change log

* Add, update or remove change log entries from your posts.
* Tag entries as minor or major in the front matter.

### Search

* Add `excluded_in_search: true` to any documentation page's front matter to exclude that page in the search results.

### Navigation

* Change `site.show_full_navigation` to control all or only the current navigation group being open.
* Sort order of navigation top level groups is determined by `category-order` on the sub-pages
* Add `excluded_in_navigation: true` to any documentation page's front matter to exclude that category in the navigation - see example on 'samples' page.

### CSS
* ForgeRock styles are layered on top of the base template. You can update variables in `css\main.scss` and add styles in `_sass\forgerock.scss`. Do not edit any of the underlying styles directly.

### Icons
* Uses google hosted material design icon font [Material Design Icons](https://material.io/icons/)
* Uses [jekyll-octicons](https://github.com/primer/octicons/tree/master/lib/jekyll-octicons). Info on available icons can be found at [https://octicons.github.com/](https://octicons.github.com/)

## To Do

- Fix site icon and touch-icon
- Design 404 page
- Consider breaking out forgerock variables from main.scss
- RSS feed integration for release info
- Integrate videos
- Integrate tests
- Create prod & staging sites
- Fix google analytics
- Set up contact email lists
- Can set up multiple doc sites
