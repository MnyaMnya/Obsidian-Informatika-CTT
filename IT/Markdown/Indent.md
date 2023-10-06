## Indent (Tab)[](https://www.markdownguide.org/hacks/#indent-tab)

Tabs and whitespace have a special meaning in Markdown. You can use trailing whitespace to create [line breaks](<Line breaks.md>), and you can use tabs to create [code blocks](Code%20blocks.md blocks>). But what if you need to indent a paragraph the old-fashioned way, using the tab key? Markdown doesn’t provide an easy way of doing that.

Your best bet might be to use a Markdown editor that supports indentation. This is common in applications that are more oriented towards desktop publishing. For example, [iA Writer](https://www.markdownguide.org/tools/ia-writer/) allows you to customize indentation settings for the editor in the application preferences. It also provides template customization options so that you can make the rendered document look the way you expect it to, indentation and all.

Another option, if your Markdown processor supports [HTML](HTML), is to use the HTML entity for non-breaking space (`&nbsp;`). This should probably be your option of last resort as it can get awkward. Basically, every `&nbsp;` in your Markdown source will be replaced with a space in the rendered output. So if you stick four instances of `&nbsp;` before a paragraph, the paragraph will look like it’s indented four spaces.

```
&nbsp;&nbsp;&nbsp;&nbsp;This is the first sentence of my indented paragraph.
```

The rendered output looks like this:

    This is the first sentence of my indented paragraph.