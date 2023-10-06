You can add emphasis by making text bold or italic.

### Bold

To bold text, add two asterisks or underscores before and after a word or phrase. To bold the middle of a word for emphasis, add two asterisks without spaces around the letters.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`I just love **bold text**.`|`I just love <strong>bold text</strong>.`|I just love **bold text**.|
|`I just love __bold text__.`|`I just love <strong>bold text</strong>.`|I just love **bold text**.|
|`Love**is**bold`|`Love<strong>is</strong>bold`|Love**is**bold|

#### Bold Best Practices

Markdown applications don’t agree on how to handle underscores in the middle of a word. For compatibility, use asterisks to bold the middle of a word for emphasis.

|✅  Do this|❌  Don't do this|
|---|---|
|`Love**is**bold`|`Love__is__bold`|

### Italic

To italicize text, add one asterisk or underscore before and after a word or phrase. To italicize the middle of a word for emphasis, add one asterisk without spaces around the letters.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`Italicized text is the *cat's meow*.`|`Italicized text is the <em>cat's meow</em>.`|Italicized text is the _cat’s meow_.|
|`Italicized text is the _cat's meow_.`|`Italicized text is the <em>cat's meow</em>.`|Italicized text is the _cat’s meow_.|
|`A*cat*meow`|`A<em>cat</em>meow`|A_cat_meow|

#### Italic Best Practices

Markdown applications don’t agree on how to handle underscores in the middle of a word. For compatibility, use asterisks to italicize the middle of a word for emphasis.

|✅  Do this|❌  Don't do this|
|---|---|
|`A*cat*meow`|`A_cat_meow`|

### Bold and Italic

To emphasize text with bold and italics at the same time, add three asterisks or underscores before and after a word or phrase. To bold and italicize the middle of a word for emphasis, add three asterisks without spaces around the letters.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`This text is ***really important***.`|`This text is <em><strong>really important</strong></em>.`|This text is _**really important**_.|
|`This text is ___really important___.`|`This text is <em><strong>really important</strong></em>.`|This text is _**really important**_.|
|`This text is __*really important*__.`|`This text is <em><strong>really important</strong></em>.`|This text is _**really important**_.|
|`This text is **_really important_**.`|`This text is <em><strong>really important</strong></em>.`|This text is _**really important**_.|
|`This is really***very***important text.`|`This is really<em><strong>very</strong></em>important text.`|This is really_**very**_important text.|

**Note:** The order of the `em` and `strong` tags might be reversed depending on the Markdown processor you're using.

#### Bold and Italic Best Practices

Markdown applications don’t agree on how to handle underscores in the middle of a word. For compatibility, use asterisks to bold and italicize the middle of a word for emphasis.