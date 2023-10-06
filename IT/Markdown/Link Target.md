Some people like creating links that open in new tabs or windows. The Markdown syntax for [links](https://www.markdownguide.org/basic-syntax/#links) doesn’t allow you to specify the `target` attribute, but if your Markdown processor supports [HTML](https://www.markdownguide.org/basic-syntax/#html), you can use HTML to create these links.

```
<a href="https://www.markdownguide.org" target="_blank">Learn Markdown!</a>
```

The rendered output looks like this:

[Learn Markdown!](https://www.markdownguide.org)