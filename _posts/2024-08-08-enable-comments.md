---
title: Enable comments in the blog
date: 2024-08-08 21:20:30+0800
categories: [Blog]
tags: [blog, comments]     # TAG names should always be lowercase
author: <admin> 
toc: true
---

Follow [Chirpy's guide](https://chirpy.cotes.page/posts/write-a-new-post/#comments).

Here are some details.

# Install Giscus

Visit <https://github.com/apps/giscus>, follow the guide, and choose the repos you want to install giscus with.

# Enable Discussions

Go to your repo -> Settings -> General -> Features, and check ``Discussions`` on, and follow the guide (keep everything as default is ok) to finish.

Then, you will see a new ``Discussions`` tab in your repo. Open this tab, create a new category named ``Comments``. Or you may also use any of the default created categories.

# Configure Giscus

Visit <https://giscus.app/>, and follow the guide.

In the seciton **Configuration**, choose your preference. Then in the subsection **Enable giscus**, you will see a auto-generated ``<script>`` like this:

``` js
<script src="https://giscus.app/client.js"
        data-repo="StoolMonster/chirpyblog"
        data-repo-id="R_kgDOMg5ddg"
        data-category="Comments"
        data-category-id="DIC_kwDOMg5dds4Che4C"
        data-mapping="title"
        data-strict="1"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
```

Make changes to ``_config.yml`` file according to ``<script>``.

 ``` yml
comments:
  # Global switch for the post comment system. Keeping it empty means disabled.
  provider: giscus # [disqus | utterances | giscus]
  # The provider options are as follows:
  disqus:
    shortname: # fill with the Disqus shortname. › https://help.disqus.com/en/articles/1717111-what-s-a-shortname
  # utterances settings › https://utteranc.es/
  utterances:
    repo: # <gh-username>/<repo>
    issue_term: # < url | pathname | title | ...>
  # Giscus options › https://giscus.app
  giscus:
    repo: StoolMonster/chirpyblog
    repo_id: R_kgDOMg5ddg
    category: Comments
    category_id: DIC_kwDOMg5dds4Che4C
    mapping: title # optional, default to 'pathname'
    strict: 1 # optional, default to '0'
    input_position: bottom # optional, default to 'bottom'
    lang: en # optional, default to the value of `site.lang`
    reactions_enabled: 1 # optional, default to the value of `1`
 ```

 Commit changes to your repo to trigger the github action to redeploy the blog.
 
 Then refresh your blog to see the result.


# References

<https://chirpy.cotes.page/posts/write-a-new-post/#comments>

<https://blog.martinp7r.com/posts/adding-giscus-comments-to-my-blog/>

<https://thiagoalves.ai/adding-comments-to-jekyll-using-giscus/>
