
To create a heading, add number signs (`#`) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (`<h3>`), use three number signs (e.g., `### My Header`).

|Markdown|HTML|Rendered Output|
|---|---|---|
|`# Heading level 1`|`<h1>Heading level 1</h1>`|# Heading level 1|
|`## Heading level 2`|`<h2>Heading level 2</h2>`|## Heading level 2|
|`### Heading level 3`|`<h3>Heading level 3</h3>`|### Heading level 3|
|`#### Heading level 4`|`<h4>Heading level 4</h4>`|#### Heading level 4|
|`##### Heading level 5`|`<h5>Heading level 5</h5>`|##### Heading level 5|
|`###### Heading level 6`|`<h6>Heading level 6</h6>`|###### Heading level 6|

### Heading Best Practices

Markdown applications don’t agree on how to handle a missing space between the number signs (`#`) and the heading name. For compatibility, always put a space between the number signs and the heading name.

|✅  Do this|❌  Don't do this|
|---|---|
|`# Here's a Heading      `|`#Here's a Heading`|

You should also put blank lines before and after a heading for compatibility.

|✅  Do this|❌  Don't do this|
|---|---|
|`Try to put a blank line before...      # Heading      ...and after a heading.`|`Without blank lines, this might not look right.   # Heading   Don't do this!`|