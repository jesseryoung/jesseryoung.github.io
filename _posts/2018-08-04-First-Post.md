---
layout: post
title: "First Post"
date: 2018-08-04
---
So, this is the first post on this site. I figured that because I went through with setting up a blog why not make a post about it. This also gives me a chance to play around with the platform and explore it a bit more.

Setting up a blog
-----------------
I actually toyed around with the idea of writing my own blog "engine" to run my blog. I figured it would make a great first post: "How to build your own blog". I attempted this several times, and each time pretty much went like this:
1. Make myself a drink.
2. Download the latest versions of .Net Core and VSCode.
3. Research some Nuget packages on how to render Markdown to html.
4. Start to write some code.
5. Realize it's been 4 hours and I'm 5 drinks deep at this point. Also I need to go to work tomorrow.
6. Forget about writing a blog for 6 months.

After noticing this pattern, I figured I'd try something a little different.

Using GitHub Pages
------------------
Using GHPages was stupid simple. Literally create a new repo on GitHub called ```<your github username>.github.io``` add an ```index.html``` and boom, you've got a site set up. Point your browser to ```https://<your github username>.github.io/``` and you'll see the content of ```index.html``` show up.

Using Your Own Domain Instead of github.io
------------------------------------------
GitHub pages supports using your own domain name for the site instead of just the ```github.io``` url. In order to set this up you need to purchase a domain from a separate provider. I use Google Domains, it's pretty straight forward to use and purchasing and managing a domain is simple for even the least tech-savvy individual.

To setup your custom domain add a CNAME record to your DNS and point it to ```<your github username>.github.io```. After that change gets propagated navigate to the settings page for your repo and scroll down the GitHub Pages section and enter your domain in the custom domain text box. I'd also recommend you turn on "Enforce HTTPS" at this point, this will add an SSL certificate to your site. This is an awesome feature that GitHub offers completely free. If you take a look at the Certificate it generates, it's actually using [Let's Encrypt](https://letsencrypt.org/) to create free SSL certificates. Cool!

Markdown + Jekyll
-----------------
GitHub Pages supports the static site generator Jekyll. You can very easily choose a theme from the settings page of your GitHub repo. This allows you write your posts as markdown instead of having to write each of your posts from scratch. Whenever you do a push with your changes GitHub will automatically build the site. 

I chose the minimal theme when setting up the site. Choosing this theme adds a ```_config.yml``` to your repo and adds a single line:
```yaml
theme: jekyll-theme-minimal
```
I made a few modifications to my site by following the directions in the [theme repo](https://github.com/pages-themes/minimal) and the [Jekyll documentation](https://jekyllrb.com/docs/home/). I also updated my ```index.md``` and added the following code block in to render the listing of my posts on the front page of the site:
```html 
{% raw %}
<ul class="posts">
    {% for post in site.posts %}
      <li>
        <a href="{{ post.url }}">{{ post.date | date: "%-d %B %Y" }} - {{ post.title }}</a>
        {{ post.excerpt }}
      </li>
    {% endfor %}
</ul>
{% endraw %}
```

Posting
-------
To add a post in Jekyll, create a folder called ```_posts``` and add a file named with the date and title of the post ending in ```.md```. For example, the filename for this post is ```2018-08-04-First-Post.md```. Add the following to the top of the file:
```yml
---
layout: post
title: "<Post Title>"
date: <Post Date>
---
```
This is called a [Front Matter Block](https://jekyllrb.com/docs/frontmatter/) and controls how the page is rendered and other configuration options. The rest of the markdown document is the post.

A few seconds after you push your new post should show up on the front page of your blog!

Wrapping Up
-----------
GitHub pages turned out to be a lot more straightforward and customizable than I thought. This was the first time I've ever interacted with Jekyll and I was easily able to get a pretty clean looking site up in just an hour or two.