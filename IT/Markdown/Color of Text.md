.## Color
Markdown doesn’t allow you to change the color of text, but if your Markdown processor supports [HTML](HTML.md), you can use the `<font>` HTML tag. The `color` attribute allows you to specify the font color using a color’s name or the hexadecimal `#RRGGBB` code.

```
<font color="red">This text is red!</font>
```

The rendered output looks like this:

This text is red!

The `<font>` HTML tag is technically supported but officially [deprecated](Deprecated.md), which means it works for now but you’re not supposed to be using it. Unfortunately, there’s not another pure HTML alternative. You could try using one of the CSS alternatives. Not all Markdown applications provide CSS support, but if the one you’re using does, here’s an alternative to the `<font>` tag:

```
<p style="color:blue">Make this text blue.</p>
```

If this is supported by your Markdown application, the output looks like this:

Make this text blue.