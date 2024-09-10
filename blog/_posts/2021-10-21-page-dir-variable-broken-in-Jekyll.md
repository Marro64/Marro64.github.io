---
layout: post
hidden: true
---

Update 2024-09-10: I opened a [GitHub issue](https://github.com/jekyll/jekyll/issues/9665) and it turns out this was an error in the documentation, my observed behaviour was expected. Turns out RTFM can't always save you.

It seems that page.dir is broken in posts? Instead of the expected output, it outputs nothing. 

This is a post generated from an .md file with the "blog" category. This can be seen in the url, _config.yml contains the line "permalink: /:categories/:slug".

The part inbetween square brackets should show the contents of page.dir ([/blog/] in this case): [{{ page.dir }}]

And as a control variable, the part inbetween square brackets should show the contents of page.url ([/blog/page-dir-variable-broken-in-jekyll] in this case): [{{ page.url }}]



Update: now removed. Old: For comparison I've added the same test to the [about page][about], which is also generated from markdown (using the same template) but not a post, instead just stored in the root folder. I've also added it to the bottom of my [portfolio page][portfolio], which is generated from html and not a post.
I've also created [this post][post] which is markdown and generated as a post (thus getting an automatic url) but has no category.

page.dir seems to work in both cases where the page is not generated from a post, but returns empty in both cases where the page is generated from a post. For testing I've commented out the permalink setting in _config.yml or remove just the category part, but this did not fix the issue.

This happens both in Jekyll 3.10.0 that GitHub Pages uses and Jekyll 4.3.3 which I use for testing.

The source for this site is over at [https://github.com/Marro64/Marro64.github.io](https://github.com/Marro64/Marro64.github.io)

[portfolio]: {{ site.url }}/portfolio
[about]: {{ site.url }}/about
[post]: {{ site.url }}/page-dir-test