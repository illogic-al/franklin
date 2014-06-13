# Franklin

Franklin is a static-site framework, optimized for online books.

![Franklin Logo](http://bitbooks.cc/images/franklin.png)

## Setup

Franklin is built on top of [Middleman](http://middlemanapp.com/), a fantastic static site generator written in Ruby. Thus the setup steps are as follows:

**1) Install Dependencies**

Ensure that you have the following installed:
* Ruby (comes pre-installed on Mac)
* Rubygems (comes pre-installed on Mac)
* Bundler (see http://bundler.io for installation instructions)

**2) Install Middleman**

```bash
# Run the following commands in the console
gem install middleman
```

For more detailed instructions, see http://middlemanapp.com/basics/getting-started/.

**3) Download this project, and place it in your ~/.middleman directory:**

```bash
# If you have git installed...
git clone git@github.com:bryanbraun/franklin.git ~/.middleman/franklin
```

If you don't have [git](http://git-scm.com/) installed, you can manually [download franklin](https://github.com/bryanbraun/franklin/archive/master.zip), unzip it, and drop it into the `.middleman` folder.

**4) Create your project and install gems:**

```bash
# Replace 'mysite' with the name of your project
middleman init mysite --template=franklin
cd mysite
bundle install
```

## Basic Usage

The most basic purpose of Franklin is to convert a stack of markdown files into an HTML site, and to do it in a way that is optimized for books.

Your markdown files go into the "source" folder. They can be named anything (`xxxxxxxx.md`), except you must have a file named `index.md` to serve as the front page of your book. Franklin starts you out with some example files, which you can change or remove to suit your needs.

The structure of your book, as given in the Table of Contents, will mimic the structure of the markdown files in the source directory. Notably:

1. Your front page (`index.md`) will be promoted to the top of the list.
2. Your readme (`readme.md`) file will not appear in your table of contents. (For guidence on how to exclude other items from the Table of Contents, see the README for the [Middleman-Navtree](https://github.com/bryanbraun/middleman-navtree) gem).

When you are ready to build your site, run the following command:
```bash
# This creates a `build` folder, containing your site, converted into static HTML.
bundle exec middleman build
```
Using Middleman's customization options, you can do all sorts of interesting things beyond this basic use-case. For details, see the [Middleman documentation](http://middlemanapp.com/).

## Configuration

Your book configuration is written in YAML and kept in /data/book.yml. This is where you can change the author, title, and other book information. The available parameters are (with example values):

```yaml
title: Example Book
author: You
github_url: https://github.com/yourname/example-book
github_pages_url: http://yourname.github.io/example-book
license_name: ''
license_url: ''
theme: glide
```

## Themes

Themes can be found in the `source/themes` directory. You can use your own theme by adding it to the `themes` folder and changing the value in `/data/book.yml` like so:

```yaml
theme: theme-name
```

Any theme you add must have the following structure:

```
theme_name
  |
  |--javascripts
  |
  |--layouts
  |
  `--stylesheets
```

The main page layout is defined in `layouts/layout.erb`. For more details on working with layouts, see [Middleman's documentation](http://middlemanapp.com/basics/templates/#layouts).

## Contribution Guidelines

1. [Fork this project](https://github.com/bryanbraun/franklin/fork)
2. Create a feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch to github (`git push origin my-new-feature`)
5. Submit a Pull Request

## Contributors

(If you are making a contribution, add your name here as part of your pull request)

## License
[MIT](http://opensource.org/licenses/MIT)
