The practice of writing in *`markdown`* is widespread because it only requires `simple syntax` to create attractive slide presentations or a _blog-post_ for example. `Markdown` is intended to be as easy-to-read and as easy-to-write as is feasible. A markdown-formatted document is practically publishable as plain text, unlike it's HTML counterpart, raw in it's native _tagged_ surroundings. To illustrate some of the features, I put together this `tutorial` loosely based on the [original spec from 2004]. To convert your document into `HTML`, [pandoc](www.pandoc.org) is your swiss-army knife of converting into all kinds of formats, various wiki formats or epub to [self-publish](https://smartblogger.com/kindle-publishing/#more-10275) for [Amazon Kindle](https://kdp.amazon.com/en_US/) for example. You can [give markdown a try]. Gone are the days when you had to learn `html` to publish a web-page!

<br/>
{{< hackcss-alert type="info" >}}
<strong>Tip:</strong> Html is awesome because of the ability to zoom in and out with most any display; hold down ctrl and = or - to adjust font-sizes. Alternatively there's ctrl'n scroll'n; hold down the ctrl key and scroll your mousewheel.
{{< /hackcss-alert >}}
  [original spec from 2004]: https://daringfireball.net/projects/markdown/syntax.text
  [give markdown a try]: https://markdown-it.github.io/

<br>
<!--more-->
Markdown's syntax has been influenced by several existing _text-to-html_ filters such as [setext](http://docutils.sourceforge.net/mirror/setext.html), [atx](http://www.aaronsw.com/2002/atx/), [textile](http://textism.com/tools/textile/), [restructuredtext](http://docutils.sourceforge.net/rst.html), [grutatext](http://www.triptico.com/software/grutatxt.html), and [ettext](http://ettext.taint.org/doc/) -- the single biggest source of inspiration for markdown's syntax is the format of plain text email.

<br>
Okay, enough with the boring stuff already. I'll be highlighting what is typed into the text editor. Note, you don't want to use a word processor, that would add alot of extraneous characters. Whats needed here is a plain text editor such as Notepad++, Atom, SublimeText or Vim_. You'll see what is served up by opening your .txt document in Firefox, Opera, Safari, Chrome or in a _color-coded_ terminal-based browser such as [Lynx](https://royal.pingdom.com/using-web-browser-lynx-visit-top-websites/). _It goes like this:_

<br>
__type:__
<br>

```md
Largest font
============
```
**to produce**

Largest font
============

**similarly,**

```md
Elements
--------
```
**or**

```md
## Elements
```
**will produce**

Elements
--------

__type__

```md
### Links
```
**to produce**

### Links

_...and so on down the line_ to `######` which produces the smallest header a.k.a. `h6`

<br>
A links' text is delimited by [square brackets] immediately followed by parentheses enclosing the url that the link points to.

```md
This is an [example](http://example.com/) of an inline link.
```
**will produce**

<br>
This is an [example](http://example.com/) of an inline link.

<br>
To create a link to a different location on the same page, this will do the trick:

<br>

```md
__Take me to the__ [Coloured Code](#Coloured_Code)
```
__Take me to the__ [Coloured Code](#Coloured_Code)

<br/>
{{< hackcss-alert type="info" >}}
<strong>Tip:</strong> Most `html` is obscured from the reader, and the same goes for the `markdown` that this page is written in. `Html`, `javascript` or `golang` plugins add functionality to the webpage if needs be.
{{< /hackcss-alert >}}

<br/>
The following can be written in html or markdown as we have seen. It's both an anchor and a header.

```
<h3 id="Emphasis">Emphasis</h3>
```

<h3 id="Emphasis">Emphasis</h3>

Markdown treats asterisks (`*`) and underscores (`_`) as indicators of emphasis. Text wrapped with one `*` or `_` is the equivalent of using html `<em>` tag. Double them up and text will be wrapped with an html `<strong>` tag like so:

```md
*single asterisks*
```
*single asterisks*

```md
_single underscores_
```
_single underscores_

```md
**double asterisks**
```
**double asterisks**

```md
__double underscores__
```
__double underscores__

```md
~~strikethrough~~
```
~~strikethrough~~


### Lists

Markdown supports ordered (numbered) and unordered (bulleted) lists.

Unordered lists can use asterisks or pluses or hyphens interchangably as list markers when followed by a space:

```md
*   apples
+   peaches
-   cherries
```

**produces:**

*   apples
+   peaches
-   cherries

Ordered lists use numbers followed by periods followed by a space and the list item. the actual numbers you use to mark the list have no effect on the html output. you could even jumble up the numbers and it would still produce an ordered list:

```md
2. Scooby
1. Dooby
4. Do
```
**produces:**

2. Scooby
1. Dooby
4. Do


As for bulleted lists, paragraphs can be wrapped with hanging indents of 4 spaces to retain the indent. Otherwise, you can be as messy as you want to be in your notes and they will order themselves into the list. List items may consist of multiple paragraphs. If subsequent paragraphs in a list item are indented by either 4 spaces (or one tab) they will be included in the bulleted paragraph:

```md
*   If something can go wrong, it will.
    If anything simply cannot go wrong, it will anyway.
    Left to themselves, things tend to go from bad to worse.
-      The chance of the bread falling with the buttered side down is directly proportional to the cost of the carpet.
The opulence of the front office decor varies
inversely with the
fundamental solvency of the firm.
* Tell a man there are 300 billion stars in the universe and he'll believe you. Tell him a bench has wet paint on it and he'll have to touch to be sure.
```

*   If something can go wrong, it will.
    If anything simply cannot go wrong, it will anyway.
    Left to themselves, things tend to go from bad to worse.
- The opulence of the front office decor varies
inversely with the
fundamental solvency of the firm.
      The chance of the bread falling with the buttered side down is directly proportional to the cost of the carpet.
* Tell a man there are 300 billion stars in the universe and he'll believe you. Tell him a bench has wet paint on it and he'll have to touch to be sure.

To put a blockquote within a list item, the blockquote's **>**
delimiters need to be indented:

```md
*   Listen, trust, do:

    > The only thing more important than your to-do list is your to-be list. The only thing more important than your to-be list is to be.”
― Alan Cohen

* We will never finish everything on our to-do lists. Such is life!
* Write another to-do list.
```
**produces:**

*   Listen, trust, do:

    > The only thing more important than your to-do list is your to-be list. The only thing more important than your to-be list is to be.”
― Alan Cohen

* We will never finish everything on our to-do lists.
* Write another to-do list.


### Inline Code

To highlight a single code command surrounded by ordinary text, wrap it with [[backtick]] quotes (`` ` ``). unlike a pre-formatted code block, a code span indicates code within a normal paragraph. It will be shown in the 'mono' font of the terminal:
Delimiters need to be indented:

```
Use the `printf()` function.
```
**produces:**

<br>
Use the `printf()` function.

<br>
The snippet of `html` code below serves as a link to the 'coloured code anchor down below. Your typlical toc- table of contents works uses these mechanics.

```html
<h3 id="Coloured_Code">Coloured Code</h3>
<!---hidden comment: I like the old spelling (shrugs)--->
```
<h3 id="Coloured_Code">Coloured Code</h3>
<!---hidden comment: I like the old spelling (shrugs)--->

Nowadays there is support for code highlighting for about 160 programming languages. this is a snippet written in [bash](https://en.wikipedia.org/wiki/bash_(unix_shell)), the commandline language of the linux shell. In addition to the three backticks you can add an abbreiviation such as `md` (for markdown) or `sh` (for the bash shell).

```sh
# To load nvm bash_completion upon login or when the file is sourced.
# add these lines to your `~/.bashrc`, `~/.profile`, or `~/.zshrc` config file
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # this loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```

I used html to create the 'Emphasis' header/anchor, but can refer back to it using a markdown link. The two are _interchangeable_.

```md
[*back up to where I was*](#Emphasis)
```

[*back up to where I was*](#Emphasis)

### Images

To insert images to your markdown file, use the markup `![alt](/path/image.ext)`. the path can either be relative to the website, or a full url for an external image. *below* is an screenshot of my desktop

<br/>
{{< hackcss-alert type="info" >}}
<strong>Tip:</strong> You can set up your desired level of transparency in your programs easily in linux. The screenshot shows my text editor, neovim, and in the layer underneath it, firefox. My Hugo sites's embedded server reflects the changes as they are typed and reflects the changes immediately in the webpage. My changes are pushed to the clould via Amazon's CodeCommit service just as soon as I issue the three familiar commands: `git add .`, git commit -m "message documenting change(s)", and `git push -u origin master`.
{{< /hackcss-alert >}}

<br/>

```md
![Semantic description of image](/images/path/to/folder/image.png "Image Title")
```
__a.k.a.__
```md
![A screenshot of the underlying code](/images/md-guide.png "Neovim on My Desktop")
```
![A screenshot of the underlying code](/images/md-guide.png "Neovim on My Desktop")

### Video

There are a couple of ways to share a video. Locally stored videos within HTML5 `<video>` tags and within `<iframe>` tags for externally hosted videos . Plain markdown results in a link to the video, whereas with a snippet of `html` we can embed video of the **author making _fruit leather_ with a homemade _solar dehydrator_.:**


```html
<iframe width="420" height="315" src="https://www.youtube.com/embed/aVHsUCALkoU" frameborder="0" allowfullscreen></iframe>
```

<br>
<iframe width="420" height="315" src="https://www.youtube.com/embed/aVHsUCALkoU" frameborder="0" allowfullscreen></iframe>

### Paragraphs and Line Breaks

A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. Normal paragraphs should not be indented with spaces or tabs.

If you want to be sure of getting empty lines between elements, insert a `<br />` _break tag_ to be certain of making blank lines.

### Tables

``` {.md}
| Left align   | Center align  | Right align    |
| :----------- | :-----------: | -------------: |
| This         | This          | This           |
| column       | column        | column         |
| will         | will          | will           |
| be bold &    | be            | be             |
| left-        | center-       | right-         |
| aligned      | aligned       | aligned        |
```

| Left align   | Center align  | Right align    |
| :----------- | :-----------: | -------------: |
| This         | This          | This           |
| column       | column        | column         |
| will         | will          | will           |
| be bold &    | be            | be             |
| left-        | center-       | right-         |
| aligned      | aligned       | aligned        |

### Blockquotes

Markdown uses email-style `>` characters for blockquoting. Blockquotes can contain other Markdown elements, including headers, lists, and code blocks. Put `>` before the first line of a _hard-wrapped_ paragraph:

```md
> Sorrow prepares you for joy. It violently sweeps everything out of your house,
so that new joy can find space to enter.
It shakes the yellow leaves from the bough of your heart, so that fresh,
green leaves can grow in their place. It pulls up the rotten roots,
so that new roots hidden beneath have room to grow.
Whatever sorrow shakes from your heart, far better things will take their place.
― Rumi
```

<br>
> Sorrow prepares you for joy. It violently sweeps everything out of your house,
so that new joy can find space to enter.
It shakes the yellow leaves from the bough of your heart, so that fresh,
green leaves can grow in their place. It pulls up the rotten roots,
so that new roots hidden beneath have room to grow.
Whatever sorrow shakes from your heart, far better things will take their place.
― Rumi
<br>
### Code Blocks

Pre-formatted code blocks are used for writing about programming or
markup source code. Rather than forming normal paragraphs, the lines
of a code block are interpreted literally. Markdown wraps a code block
in both `<pre>` and `<code>` `html` tags.

To produce a code block in markdown, simply indent every line of the
block by at least 4 spaces or 1 tab.

```html
    <div class="footer">
        &copy; 2004 foo corporation
    </div>
```

**will produce this:**

    <div class="footer">
        &copy; 2004 foo corporation
    </div>

<br>

A code block continues until it reaches a line that is not indented
(or the end of the article).
To put a code block in a list, the code block needs to be indented *twice* -- 8 spaces or two tabs.

<br>



### Backslash Escapes

Regular markdown syntax is not processed within code blocks. e.g., asterisks are just literal asterisks within a code block. This means it's also easy to use markdown to write about markdown's own syntax.
Outside of code blocks you can use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown’s formatting syntax. For example, if you wanted to surround a word with literal asterisks (instead of an HTML <em> tag), you can use backslashes before the asterisks, like this:

```md
\*literal asterisks\*
```

\*literal asterisks\*

<br/>
Escape the following character with backslashes when you want to be sure they're interpereted literally:

\\   backslash
\`   backtick
\*   asterisk
\_   underscore
\{}  curly braces
\[]  square brackets
\()  parentheses
\#   hash mark
\+   plus sign
\-   minus sign (hyphen)
\.   dot
\!   exclamation mark

<br>
Lines across the page with either of:
```md
***
---
```

***
---



