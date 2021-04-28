This document is best veiwed in a html browser to experience the quality of Markdown.

Markdown has gained much traction due to it's simple syntax and ease of use. You can edit Markdown in plain text, unlike `HTML` with it's _taggy_ surrounds. *Hyperlinks* to other documents and urls are retained without affecting readability. Other attributes will be `color-coded` in your text editor. Nowadays, markdown is widely used for project documentation, jupyter notebooks and rendering static webpages (like this one!) on modern [web frameworks](https://jamstack.org/). It is super useful for [*vimwiki*](https://mkaz.blog/working-with-vim/vimwiki/), a personal text-based *wiki plugin* for [Vim](https://www.vim.org/). 

<br/>
{{< hackcss-alert type="success" >}}
<strong>Code Tip:</strong> 
Use the following command to extract the articles in *clean markdown* from a folder of `.html` documents (you will need `rdrview` (from github) and `pip install html2markdown`):
<br/>
`for i in *.html ; do echo "$i" && rdrview --template=title,sitename,byline,body -H $i | html2markdown --no-skip-internal-links --no-automatic-links --no-wrap-links --ignore-images --unicode-snob --mark-code --body-width=0 --single-line-break --decode-errors=ignore > $i.md ; done`
{{< /hackcss-alert >}}

This guide will help you get to grips with writing markdown for yourself. 

<!--more-->

>  For more ambitious [self-publishing] projects like an ebook, you can leverage other tools like `docbook`, `asciidoc`. [Pandoc](https://pandoc.org/) for example, can [reliably convert](https://jdhao.github.io/2019/05/30/markdown2pdf_pandoc/) .md into `HTML`, `pdf`, `epub`, `wiki` or myriad of other formats. 
  [self-publishing]: https://smartblogger.com/kindle-publishing/#more-10275
  
<br/>
All you need to get started is a `plain text` editor such as Notepad++, Atom, SublimeText or Vim. You don't want to use a word processor, that would add extraneous characters. 
<br/>

__Let's do this!__


### Headers
<br>
__type this:__
<br>

```md
Largest font
============
```
**to produce this:**

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
**and we get**

Elements
--------

__Type__

```md
### Links
```
**to produce**

### Links

_...and so on down the line_ to `######` which produces the smallest header a.k.a. `H6`. Now that we're on the subject, a links' text is delimited by square brackets immediately followed by parentheses enclosing the url that the link points to.

```md
A [generic](http://example.com/) link.
```
**will produce**

<br/>

A [generic](http://example.com/) link.

<br/>

Not that you want to go before my fascinating tutorial is over!  To provide a link lower down on the page, the following will do the trick.


<br/>

```md
__Take me to the__ [Coloured Code](#Coloured_Code)
<!---hidden note: I like the old spelling (shrugs)--->
```
__Take me to the__ [Coloured Code](#Coloured_Code)

<br/>
{{< hackcss-alert type="warning" >}}
<strong>Much More Than Meets The Eye:</strong> Most HTML is obscured from the reader, and also to a lesser extent the markdown that underlies this page. Javascript and other platform-specific components can add functionality to otherwise static webpages.
{{< /hackcss-alert >}}

<br/>
The following can be written in HTML or markdown as we have seen. It's both an anchor and a header.

```html
<h3 id="Emphasis">Emphasis</h3>
```

<h3 id="Emphasis">Emphasis</h3>

Markdown treats asterisks (`*`) and underscores (`_`) as indicators of emphasis. Text wrapped with one `*` or `_` is the equivalent of using HTML `<em>` tag. Double them up and text will be wrapped with an HTML `<strong>` tag like so:

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

Ordered lists use numbers followed by periods followed by a space and the list item. the actual numbers you use to mark the list have no effect on the HTML output. you could even jumble up the numbers and it would still produce an ordered list:

```md
2. Scooby
1. Dooby
4. Do
```
**produces:**

2. Scooby
1. Dooby
4. Do


List items may consist of multiple paragraphs. Paragraphs can be neatly wrapped with hanging indents of 4 spaces. Or your notes can be as messy as mine. Order will be available when the markdown has been interpereted.If subsequent paragraphs in a list item are indented by either 4 spaces (or one tab) they will be included in the bulleted paragraph:

```md
*   If something can go wrong, it will.
    If anything simply cannot go wrong, it will anyway.
    Left to themselves, things tend to go from bad to worse.
-     The opulence of the front office decor varies
inversely with the
fundamental solvency of the firm.
      The chance of the bread falling with the buttered side down being directly proportional to the cost of the carpet.
* Tell a man there are 300 billion stars in the universe and he'll believe you. Tell him a bench has wet paint on it and he'll have to touch to be sure.
```

*   If something can go wrong, it will.
    If anything simply cannot go wrong, it will anyway.
    Left to themselves, things tend to go from bad to worse.
- The opulence of the front office decor varies
inversely with the
fundamental solvency of the firm.
      The chance of the bread falling with the buttered side down being directly proportional to the cost of the carpet.
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

### Emoji

I enabled emojis in my [hugo] config file with `enableEmoji = true`. ~~I was going for :thinking_face: but apparently that one isn't supported yet (your mileage may vary). Instead,~~ I present `japanese_ogre`.

<br/>
:japanese_ogre:

### Inline Code

To highlight a single code command surrounded by ordinary text, wrap it with backtick quotes (`` ` ``). Unlike a pre-formatted code block, a code span indicates code within a normal paragraph. It will be shown in the 'mono' font of the terminal:
Delimiters need to be indented:

```
Use the `printf()` function.
```
**produces:**

<br>
Use the `printf()` function.

<br>
This snippet of `HTML` code is an anchor or an embedded `id` and a H3 header. A TOC, or table of contents, uses internal page links. It could also be written in `markdown`, same difference! (The HTML tags get added when the page is run through a processor):

```md
[*Coloured_Code*](#Coloured Code)
```

```html
<h3 id="Coloured_Code">Coloured Code</h3>
<!---hidden comment: I like the old spelling (shrugs)--->
```
<h3 id="Coloured_Code">Coloured Code</h3>
<!---hidden comment: I like the old spelling (shrugs)--->


Nowadays there is support for code highlighting for about 160 programming languages. this example is written in [bash](https://en.wikipedia.org/wiki/bash_(unix_shell)), the commandline language of the linux shell. In addition to the three backticks you can add an abbreviation such as `md` (markdown) or `sh` (to highlight code written in bash). I'll show the backticks that are required to create a code box (they are just for illustration and have to be escaped by `\` so as not to be interpreted as 'special characters').

```sh
\```sh
# To load nvm bash_completion upon login or when the file is sourced.
# add these lines to your `~/.bashrc`, `~/.profile`, or `~/.zshrc` config file
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # this loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
\```
```

The 'Emphasis' header/anchor was created using a HTML snippet, but we can also get around using markdown:

```md
[*back up to where I was*](#Emphasis)
```

[*back up to where I was*](#Emphasis)

### Images

To insert images to your markdown file, use the markup `![alt](/path/image.ext)`. the path can either be relative to the website, or a full url for an external image. *Below* is a screenshot of my current desktop.

<br/>

```md
![Semantic description of image](/images/path/to/folder/image.png "Image Title")
```
__a.k.a.__
```md
![A screenshot of the underlying code](/images/md-guide.png "Neovim on My Desktop")
```
![A screenshot of the underlying code](/images/md-guide.png "Neovim on My Desktop")

<br/>
{{< hackcss-alert type="success" >}}
<strong>Cool Tip:</strong> Set your program windows to 70% transparency in linux. The top layer shows my text editor, neovim, underneath is the HTML translation in firefox. On the bottom layer, a random slide-show of hand-picked artwork.
{{< /hackcss-alert >}}

### Video

There are a couple of ways to share a video. I can use a `shortcode` provided in the [Hugo] static site generator. Plain markdown results in a link to the video, but with HTML5 tags we can embed this video of the **author making _fruit leather_ with a homemade _solar dehydrator_.:**


```html

<iframe width="1059" height="480" src="https://www.youtube.com/embed/aVHsUCALkoU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

```
<iframe width="1059" height="480" src="https://www.youtube.com/embed/aVHsUCALkoU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>

### Paragraphs and Line Breaks

A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. Normal paragraphs should not be indented with spaces or tabs.

If you want to be sure of getting empty lines between elements, insert a `<br />` _break tag_ to be certain of making blank lines.

### Tables

``` {.md}
| Left         | Center        | Right          |
| :----------- | :-----------: | -------------: |
| This         | This          | This           |
| column       | column        | column         |
| will         | will          | will           |
| be bold &    | be            | be             |
| left-        | center-       | right-         |
| aligned      | aligned       | aligned        |
```

| Left         | Center        | Right          |
| :----------- | :-----------: | -------------: |
| This         | This          | This           |
| column       | column        | column         |
| will         | will          | will           |
| be bold &    | be            | be             |
| left-        | center-       | right-         |
| aligned      | aligned       | aligned        |

If you want to format text on a particular way on the page, one way to do it is create a table with those proportions (your table will span the width of the page). Set the border of the table to 0px in your CSS and the table edges will not be visible, but the text will.

<br\>
### Blockquotes

Markdown uses email-style `>` characters for blockquoting. Blockquotes can contain other Markdown elements, including headers, lists, and code blocks. Put `>` before the first line of a _hard-wrapped_ paragraph:

```md
>    Sorrow prepares you for joy. It violently sweeps everything out of
>  your house, so that new joy can find space to enter.
>  It shakes the yellow leaves from the bough of your heart, so that fresh,
>  green leaves can grow in their place. It pulls up the rotten roots,
>  so that new roots hidden beneath have room to grow.
>  Whatever sorrow shakes from your heart, far better things will take their place.
<br>
>    ~Rumi
```
<br>

>    Sorrow prepares you for joy. It violently sweeps everything out of
>  your house, so that new joy can find space to enter.
>  It shakes the yellow leaves from the bough of your heart, so that fresh,
>  green leaves can grow in their place. It pulls up the rotten roots,
>  so that new roots hidden beneath have room to grow.
>  Whatever sorrow shakes from your heart, far better things will take their place.
<br>
>                                  ~Rumi

<br>
### Code Blocks

Pre-formatted code blocks are used for writing about programming and source code. Rather than forming normal paragraphs, the lines are  wrapped in `<pre>` and `<code>` `HTML` tags to be interpreted literally. To get the result, indent every line of the block by at least 4 spaces or 1 tab.

```
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

