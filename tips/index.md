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

  - `site.pages`: Holds each page on the site and all related info.
    Sample value: {{site.pages}}
  - `site.data`: Any `.yml`, `.csv`, or `.json` data loaded from files in the `_data/` path.
