## Getting Started

* clone down this repo
* `gem install jekyll`
* To preview what you're starting with, make sure you're inside of this directory, then run `jekyll serve`. You'll see a `_site` folder created. Don't modify anything inside this folder. This is the static HTML that will be generated based on what you have in the `_includes`, `_layouts`, and `_posts` folders, as well as `index.md` which is your root page. Navigate to `localhost:4000` and you'll see your site. 

### Modifying Content

* `index.html` is your landing page. Right now, this is what you see inside:

```html
{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <h4>{{ post.date | date: "%m-%d-%Y" }}</h4>
  <p>{{ post.content | strip_html | truncatewords:10}}</p>
{% endfor %}
```

This bit of code will iterate over all of the html files in the `_posts` folder and create an `<h2>` with the title of the post, an `<h4>` with the formatted date, and a 10-word preview of the post's content. 

* The `_posts` folder is where all of your blog entries are kept. The filename format is `yyyy-mm-dd-post-title.html`. Feel free to change the filename as long as you also change the headers at the top of the file to match:

```html
---
title: My First Post
layout: post
date: 2015-11-25
---
```

Delete the filler content in the file and replace it with the text for your blog post. You can create more post files using the `yyyy-mm-dd-post-title.html` format. **Posts with dates in the future will not show up.**

* `_includes` contains the `header.html` and `footer.html` for your page. You might want to consider adding a navbar inside of the header, and contact info inside of the footer. Notice that the tags in the footer close those in the header. The bit `{{ site.title }}` inside of `header.html` comes from the `_config.yml` file. If you'd like to change the title, change it inside the config file. 

* `_layouts` contains different layouts you can use. Right now, there is a `default.html` layout and a `post.html` layout. Default is used for the landing page (`index.html`), whereas post layout is used for the files inside of `_posts`. You can specify the layout to use in the headers:

```html
---
title: My First Post
layout: post
date: 2015-11-25
---
```

* Don't modify anything inside of the `_site` folder. This folder is auto-generated by Jekyll. Running `jekyll serve` from the command line will automatically generate this folder. Before pushing up to GitHub, make sure that this folder is up to date with your changes by running `jekyll build`. 

### Modifying Style

* The `css` folder contains one stylesheet: `styles.css`. You can add styles inside of this file like so:

```css
body {
  background-color: red;
}
```

(but please don't actually make your background color red)

* If you choose to add another stylesheet, make sure to add a `<link rel="stylesheet" href="">` inside of the `header.html` file. 

# chompasina.github.io
