Markdown [tables](Tables.md) are notoriously finicky. You can’t use many Markdown syntax elements to format the text in table cells. But there are workarounds for at least two common table issues: Line breaks and lists.

### Line Breaks Within Table Cells[](https://www.markdownguide.org/hacks/#line-breaks-within-table-cells)

You can separate paragraphs within a table cell by using one or more `<br>` HTML tags.

```
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| Paragraph   | First paragraph. <br><br> Second paragraph. |
```

The rendered output looks like this:

|Syntax|Description|
|---|---|
|Header|Title|
|Paragraph|First paragraph.  <br>  <br>Second paragraph.|

### Lists Within Table Cells[](https://www.markdownguide.org/hacks/#lists-within-table-cells)

You can add a list within a table cell by using HTML tags.

```
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| List        | Here's a list! <ul><li>Item one.</li><li>Item two.</li></ul> |
```

The rendered output looks like this:

|Syntax|Description|
|---|---|
|Header|Title|
|List|Here's a list!<br><br>- Item one.<br>- Item two.|

## Table of Contents[](https://www.markdownguide.org/hacks/#table-of-contents)

Some Markdown applications like [Markdeep](https://www.markdownguide.org/tools/markdeep/) can automatically generate a table of contents (also referred to as a _toc_) from your [headings](https://www.markdownguide.org/basic-syntax/#headings), but this isn’t a feature provided by all Markdown applications. However, if your Markdown application supports [heading IDs](https://www.markdownguide.org/extended-syntax/#heading-ids), you can create a table of contents for your Markdown file using a [list](https://www.markdownguide.org/basic-syntax/#lists-1) and some [links](https://www.markdownguide.org/basic-syntax/#links).

```
#### Table of Contents

- [Underline](#underline)
- [Indent](#indent)
- [Center](#center)
- [Color](#color)
```

The rendered output looks like this:

#### Table of Contents

- [Underline](https://www.markdownguide.org/hacks/#underline)
- [Indent](https://www.markdownguide.org/hacks/#indent)
- [Center](https://www.markdownguide.org/hacks/#center)
- [Color](https://www.markdownguide.org/hacks/#color)