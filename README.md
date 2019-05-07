# ForgeRock EA Documentation

https://forgecloud.github.io/

This is the Early Access developer docs site for the ForgeRock Identity Cloud. This project uses Jekyll to generate HTML files from markdown.

## Work in Progress

You can find the current work in progress in the `staging` branch. To review the content as shown in a browser, you'll have to pull that branch and build the doc yourself, as described in the ## Setup section.


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

If you're trying out changes, add the `--incremental` or `-I` switch to the end of that command. When you save changes to a file, you'll see the changes when you refresh your browsser.

~~~bash
$ bundle exec jekyll serve -I
~~~

If you do not see changes after refreshing your browser, you may need to rebuild the docs. To do so, stop the `bundle exec jekyll serve` process and run the following command:

~~~bash
$ bundle exec jekyll clean
~~~

Subsequent uses of `bundle exec jekyll serve` should work.


### Learn about Jekyll

* Learn Jekyll with step-by-step tutorials and videos at [Jekyll Tips](http://jekyll.tips/).
* Jekyll cheat sheet [Jekyll Cheat Sheet](https://learn.cloudcannon.com/jekyll-cheat-sheet/).
* http://127.0.0.1:4000/samples/sample-page/ folder contains examples of URLs, links, and formatting.

### Documentation page.

* Add, update or remove a documentation page in the *Documentation* collection.
* Change the category of a documentation page to move it to another section in the navigation.
* Documentation pages are organized in the navigation by category, with URLs based on the path inside the `_docs` folder.

### Change log

* Add, update or remove change log entries from your posts.
* Tag entries as minor or major in the front matter.
* Adding items 
* Add `excluded_in_search: true` to any documentation page's front matter to exclude that page in the search results.

### Navigation

* Change `site.show_full_navigation` to control all or only the current navigation group being open.
* Sort order of navigation top level groups is determined by `category-order` on the sub-pages.
* Add `excluded_in_navigation: true` to any documentation page's front matter to exclude that category in the navigation - see example on 'samples' page.

### CSS
* ForgeRock styles are layered on top of the base template. You can update variables in `css\main.scss` and add styles in `_sass\forgerock.scss`. Do not edit any of the underlying styles directly.

### Icons
* Uses google hosted material design icon font [Material Design Icons](https://material.io/icons/).
* Uses [jekyll-octicons](https://github.com/primer/octicons/tree/master/lib/jekyll-octicons). Info on available icons can be found at [https://octicons.github.com/](https://octicons.github.com/).

### Style Linter

You can now test changes with a lightweight custom implementation of the [Vale](https://github.com/errata-ai/vale) syntax-aware prose linter. It does not yet include most elements of the internal ForgeRock style guide.

Once you've installed `vale` as described in the [Vale](https://github.com/errata-ai/vale) GitHub repository, you can use it to check the syntax of the file of your choice. For example, to review the syntax of the [Architecture](https://developer-cloud.forgerock.com/overview/architecture/) overview page, navigate to the path of this repository and run the following command:

$ `vale _docs/overview/architecture.md`

### PlantUML

Jekyll supports the use of the [PlantUML](http://plantuml.com/) sequence diagram tool. As we use PlantUML in our product and platform docs, it's a useful feature especially when describing OAuth2 / OIDC sequences. 

To set up PlantUML, you'll need:
- PlantUML Gem
- *plantuml.jar* 
- A script named *plantuml* that refers to the JAR file, with `java -jar /usr/local/bin/plantuml.jar "$1" "$2"`
- Include the jekyll-plantuml gem in the following files: _config.yml and GEMFILE.
- [GraphViz](https://www.graphviz.org/) graph visualization software.

## To Do

- Fix site icon and touch-icon.
- Consider breaking out forgerock variables from main.scss.
- Fix google analytics.
