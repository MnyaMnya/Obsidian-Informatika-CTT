
You can organize items into ordered and unordered lists.

### Ordered List
To create an ordered list, add line items with numbers followed by periods. The numbers don’t have to be in numerical order, but the list should start with the number one.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`1. First item   2. Second item   3. Third item   4. Fourth item`|`<ol>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ol>`|1. First item<br>2. Second item<br>3. Third item<br>4. Fourth item|
|`1. First item   1. Second item   1. Third item   1. Fourth item`|`<ol>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ol>`|1. First item<br>2. Second item<br>3. Third item<br>4. Fourth item|
|`1. First item   8. Second item   3. Third item   5. Fourth item`|`<ol>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ol>`|1. First item<br>2. Second item<br>3. Third item<br>4. Fourth item|
|`1. First item   2. Second item   3. Third item       1. Indented item       2. Indented item   4. Fourth item`|`<ol>     <li>First item</li>     <li>Second item</li>     <li>Third item       <ol>         <li>Indented item</li>         <li>Indented item</li>       </ol>     </li>     <li>Fourth item</li>   </ol>`|1. First item<br>2. Second item<br>3. Third item<br>    1. Indented item<br>    2. Indented item<br>4. Fourth item|

#### Ordered List Best Practices

CommonMark and a few other lightweight markup languages let you use a parenthesis (`)`) as a delimiter (e.g., `1) First item`), but not all Markdown applications support this, so it isn’t a great option from a compatibility perspective. For compatibility, use periods only.

|✅  Do this|❌  Don't do this|
|---|---|
|`1. First item   2. Second item`|`1) First item   2) Second item`|

### Unordered Lists

To create an unordered list, add dashes (`-`), asterisks (`*`), or plus signs (`+`) in front of line items. Indent one or more items to create a nested list.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`- First item   - Second item   - Third item   - Fourth item`|`<ul>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ul>`|- First item<br>- Second item<br>- Third item<br>- Fourth item|
|`* First item   * Second item   * Third item   * Fourth item`|`<ul>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ul>`|- First item<br>- Second item<br>- Third item<br>- Fourth item|
|`+ First item   + Second item   + Third item   + Fourth item`|`<ul>     <li>First item</li>     <li>Second item</li>     <li>Third item</li>     <li>Fourth item</li>   </ul>`|- First item<br>- Second item<br>- Third item<br>- Fourth item|
|`- First item   - Second item   - Third item       - Indented item       - Indented item   - Fourth item`|`<ul>     <li>First item</li>     <li>Second item</li>     <li>Third item       <ul>         <li>Indented item</li>         <li>Indented item</li>       </ul>     </li>     <li>Fourth item</li>   </ul>`|- First item<br>- Second item<br>- Third item<br>    - Indented item<br>    - Indented item<br>- Fourth item|

#### Starting Unordered List Items With Numbers[](https://www.markdownguide.org/basic-syntax/#starting-unordered-list-items-with-numbers)

If you need to start an unordered list item with a number followed by a period, you can use a backslash (`\`) to [escape](Escaping%20Characters.md Characters>) the period.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`- 1968\. A great year!   - I think 1969 was second best.`|`<ul>     <li>1968. A great year!</li>     <li>I think 1969 was second best.</li>   </ul>`|- 1968. A great year!<br>- I think 1969 was second best.|

#### Unordered List Best Practices[](https://www.markdownguide.org/basic-syntax/#unordered-list-best-practices)

Markdown applications don’t agree on how to handle different delimiters in the same list. For compatibility, don’t mix and match delimiters in the same list — pick one and stick with it.

|✅  Do this|❌  Don't do this|
|---|---|
|`- First item   - Second item   - Third item   - Fourth item`|`+ First item   * Second item   - Third item   + Fourth item`|