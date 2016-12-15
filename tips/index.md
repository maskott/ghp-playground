---
layout: default
title: "Jekyll Tips"
---
Just some stuff I did in Jekyll to make things work.

For instance:

- To get everything serving over https, I had to use a `replace` filter on the variable for the site root as such:

    ```
    {% raw %}{{ '/css/main.css' | prepend: site.github.url | replace: 'http://', '//' }}{% endraw %}
    ```

- {% assign openTag = '{%' %}To escape double curly brackets while writing code examples like the one above, use `{{ openTag }} raw %}` and `{{ openTag }} endraw %}` around the code.

- Some important variables:

  - `site.pages`: Holds actual content of each page on the site and all related info.
  - `site.data`: Any `.yml`, `.csv`, or `.json` data loaded from files in the `_data/` path.
  

- As seen in [this StackOverflow](http://stackoverflow.com/questions/24098792/how-to-force-github-pages-build) you can use the following to make an empty commit and trigger a Jekyll rebuild in Github Pages. *It may still take a few miniutes to build.*
```sh
git commit -m 'rebuild pages' --allow-empty
```

- Last Modified at: {{ page.last_modified_at | date: '%Y:%B:%A:%d:%S:%R' }}
