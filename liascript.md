# Liascript documentation

In this document you will find to use a liascript features and how to create a liascript document using markdown.

## **Table of contents**

* [**Introduction**](#introduction)
* [**Editors**](#editors)
* [**Markdown Syntax**](#markdown-syntax)

## **Introduction**

---

**What is LiaScript?**

* A Markdown dialect for interactive courses and data-driven publishing,
* Everything is implemented in Elm/JavaScript and runs directly within the browser (online),
* The interpreter itself is also a reader, which allows for storing documents as well as the progress,
* Courses can also be taken offline, since the interpreter is also a progressive web app (PWA), that allows to store documents and progress directly within the browser (locally),
* Everything is private, we do not store any data about the courses nor the users and their progress

---

**What is Markdown?**

* A simple markup language, which is easy to learn and to use, but also very powerful, since it can be extended with HTML, CSS, JavaScript, and other languages.
* It is used by many platforms, such as GitHub, GitLab, StackOverflow, and many more.
* It is also used by many static site generators, such as Jekyll, Hugo, and many more.
* It is also used by many blogging platforms, such as Ghost, WordPress, and many more.

---

## **Editors**

---

1. **Visual-Studio-Code**: This is Microsofts new flagship with various plugins and extensions. click on the [link](https://code.visualstudio.com/Download) to download the visual studio code.

   1. [liascript-preview](https://marketplace.visualstudio.com/items?itemName=LiaScript.liascript-preview):
      Is a tiny previewer that, if it was toggled ( `Alt+L` ), updates the view
      on your course each time you save your document.
   2. [liascript-snippets](https://marketplace.visualstudio.com/items?itemName=LiaScript.liascript-snippets):
      If you start typing `lia` in your Markdown document you switch on a fuzzy
      search, that contains a lot of LiaScript help, examples, and snippets.

   Detailed installation instructions can be found [here](https://aizac.herokuapp.com/install-visual-studio-code-with-liascript/).

---

2. **Atom**: This is a very popular editor, which is also based on the electron framework. click on the [link](https://atom.io) to download the atom editor.

    1. [liascript-preview](https://github.com/andre-dietrich/liascript-preview):
      Is a tiny previewer that, if it was toggled ( `Alt+L` ), updates the view
      on your course each time you save your document.
    2. [liascript-snippets](https://github.com/andre-dietrich/liascript-snippets):
      If you start typing `lia` in your Markdown document you switch on a fuzzy
      search, that contains a lot of LiaScript help, examples, and snippets.

    Detailed installation instructions can be found [here](https://aizac.herokuapp.com/install-atom-with-liascript/).

---

                           --{{0}}--
There are currently 2 plugins for the [Atom Editor](https://atom.io) and
[Visual-Studio-Code](https://code.visualstudio.com/Download) available, which
are intended to ease and simplify the development of online courses with
LiaScript. 

## **Markdown Syntax**

* [**Basic Definition on top of the document**](#basic-definition-on-top-of-the-document)
* [**Headings**](#headings)
* [**Text**](#text)
* [**Escape Characters**](#escape-characters)
* [**Lists**](#lists)
* [**Links**](#links)
* [**Images**](#images)
* [**Tables**](#tables)
* [**Code**](#code)
* [**Blockquotes**](#blockquotes)

### **Basic Definition on top of the document**

---

                          --{{0}}--
This section is intended to give a brief overview on the basic Markdown syntax
elements. The only difference to common Markdown at this point is, that you can
define meta-information such as author, language, voice, etc. within a
HTML-comment at the beginning of every document. We will describe all of these
elements in more detail in [section: Macros](#macros). All of these `macros`
start with a single word, which is followed by a colon. If you require more
space, like for `comment:` or `link:` you can use multiple lines, but every
following line has to start with an indentation.

Initial LIA-comment-tag for basic definitions:

``` XML
<!--

author:   Andre Dietrich

email:    LiaScript@web.de

version:  0.0.1

language: en

narrator: US English Female

comment:  Write a short abstract of your course, that
          might contain multiple lines and sentences.

script:   https://javascript_resourse_url

script:   https://another_javascript_resourse_url

link:     https://some_css_stuff
          https://and_some_more_css
-->
```

---

### **Headings**

---

Syntax for headings:

``` markdown    
#
```

Headings are defined by a single `#` at the beginning of a line. The number of `#` defines the level of the heading. The following example shows the usage of headings.

``` Markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---

### **Text**

---

                            --{{0}}--
How does text-highlighting work in a text file and thus within a paragraph?
Well, Markdown defines some basic characters that can be used to surround a word
or a collection of words. We tried to use the GitHub flavored Markdown style for
simple formatting, thus simply use multiple asterisks or underscores to mark
certain parts of a text.

Text is written as usual, but you can also use some special syntax to highlight text. The following example shows the usage of text.

* `*italic*` -> *italic*
* `**bold**` -> **bold**
* `***bold and italic ***` -> ***bold and italic ***
* `_also italic_` -> _also italic_
* `__also bold__` -> __also bold__
* `___also bold and italic___` -> ___also bold and italic___
* `~strike~` -> ~strike~
* `~~underline~~` -> ~~underline~~
* `~~~strike and underline~~~` -> ~~~strike and underline~~~
* `^superscript^` -> ^superscript^
* `**bold _bold italic_**` -> **bold _bold italic_**
* `**~bold strike~ ~~bold underline~~**` -> **~bold strike~ ~~bold underline~~**
* `*~italic strike~ ~~italic underline~~*` -> *~italic strike~ ~~italic underline~~*

---

### **Escape Characters**

                          --{{0}}--
If you want to use asterisks, hash-tags, or other syntax elements within your
document without applying their functionality, then you can escape or in other
words indicate them with a starting backslash. If you want to escape a
backslash, you will have to write two subsequent backslashes. But you do not
have to use it, if there is only one asterisk within a line, this will be
interpreted as a single character. So you will have to apply this kind of
escaping only to prevent misunderstandings between you and the interpreter.

**Markdown-Syntax:**

```md
\
```

``` markdown
\*, \~, \_, \#, \{, \}, \[, \], \|, \`, \$, \@, \\, \<, \>
```

**Result:** \*, \~, \_, \#, \{, \}, \[, \], \|, \`, \$, \@, \\, \<, \>

### **Lists**

---

syntax for lists:

``` markdown
* , - , +
```

                          --{{0}}--
The GitHub-flavored Markdown supports two types of lists, ordered and unordered
ones, and so does LiaScript. If you every used a typewriter then the following
syntax for lists would look natural to you. The only thing that matters here is
the correct indentation.

> **Use spaces for correct indentation!** Tabs are allowed too, but might be
> confusing, since editors tend to use varying lengths from 2 to 4 spaces to
> display them...

---

#### **Unordered Lists**

---

                          --{{0}}--
To define an unordered list, starting asterisks `*`, pluses `+`, and dashes `-`
can be used and mixed. If one point has more than one line, you can also use
multiple lines to define paragraphs. All other Markdown elements, you will get
to know, can be included in the same way.

**Markdown-Syntax:**

``` markdown
* alpha
+ **beta**
- gamma
  and delta

  new Paragraph

  - and another
  - important list

- epsilon
```

**Result:**

* alpha
+ **beta**
- gamma
  and delta

  new Paragraph

  - and another
  - important list

- epsilon

> __Note:__
> At the moment it is required to separate blocks by at least one empty line.
> The following example will be interpreted as a single paragraph:
>
> ``` markdown
> * this is one single
>   - paragraph with a dash.
> ```
>
> Whereby the following will result in a bullet point with another one nested
>
> ``` markdown
> * separate paragraph
>
>   - and this is a separate sub listing
> ```

---

#### **Ordered Lists**

---

                          --{{0}}--

Ordered lists start with a number and a dot. As you can see from the example,
the numbering is important. In contrast to the GitHub flavored Markdown or the
original Markdown, where the list below would result in **two** separate lists,
and the numbering for every list would start at 1, ignoring your numbering
order. With the LiaScript interpretation you can separate your lists, add more
explanations in between, or use animations to make certain parts appear or
disappear.


**Markdown-Syntax:**

``` markdown
0. alpha
1. **beta**

Something else ...

3. * gamma
   * delta
   * and epsilon
2. probably zeta
```

**Result:**

0. alpha
1. **beta**

Something else ...

3. * gamma
   * delta
   * and epsilon
2. probably zeta

---

### **Links**

---

                          --{{0}}--
There are two ways of adding links to a Markdown document, either by inlining
the URL directly or you can name it (as shown in listing 2), by applying the
typical brackets and parenthesis notation, the optional information is put in
double quotes at the end of the URL. This optional information is used as a
title attribute, and it is shown, when the user hovers the link with the mouse.


syntax for links:

``` markdown
http://goo.gl/fGXNvu
*** http://goo.gl/fGXNvu ***
[title](http://goo.gl/fGXNvu "optional info")
[next slide](#18)
```

1. Example of an URL-link -> http://goo.gl/fGXNvu

   text-formatting can be applied also `*** http://goo.gl/fGXNvu ***` ->
   *** http://goo.gl/fGXNvu ***

2. Naming the link (`[title](http://goo.gl/fGXNvu "optional info")`) ->
   [title](http://goo.gl/fGXNvu "optional info")

3. For internal navigation you can refer to the slide number or to title with
   a starting `#`

   * `[next slide](#18)` -> [next slide](#14)

---

### **Images**

---

**Image-notation:**

``` markdown
![alt-text](url) 
![alt-text](url "optional title")
```

* relative URL: `![Beautiful Lenna](img/lenna.jpg)`

  ![Beautiful Lenna](img/lenna.jpg)

* absolute URL: `![Annunciation of ...](https://upload.wiki...jpg)`

  ![Annunciation of the brith of Christ](https://upload.wikimedia.org/wikipedia/commons/5/51/Leonardo_da_Vinci_Annunciation.jpg "**Annunciation c. 1472–1476**: is thought to be Leonardo's earliest complete work")

---

**Galleries**


                          --{{0}}--
How would you interpret a paragraph full of images? We thought that the only
reasonable depiction of this could be a gallery.

``` markdown
![img1](url) ![img2](url) ![img3](url)
![img4](url)
![img5](url)
```

And we like this idea... You can click on every image and inspect it also with
the zooming feature.

![Portrait of a lady](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Leonardo_da_Vinci_%28attrib%29-_la_Belle_Ferroniere.jpg/723px-Leonardo_da_Vinci_%28attrib%29-_la_Belle_Ferroniere.jpg "La Belle Ferronnière, c. 1490–1498")
![Lady with an Ermine](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f9/Lady_with_an_Ermine_-_Leonardo_da_Vinci_-_Google_Art_Project.jpg/761px-Lady_with_an_Ermine_-_Leonardo_da_Vinci_-_Google_Art_Project.jpg "Lady with an Ermine, c. 1489–1491, Czartoryski Museum, Kraków, Poland")
![Mona Lisa](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg/687px-Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg "Mona Lisa or La Gioconda c. 1503–1516, Louvre, Paris")
![Virgin and Child ](https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg/764px-Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg "The Virgin and Child with Saint Anne, c. 1501–1519, Louvre, Paris")
![The Death of Leonardo da Vinci](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Francois_Ier_Leonard_de_Vinci-Jean_Auguste_Dominique_Ingres.jpg/1276px-Francois_Ier_Leonard_de_Vinci-Jean_Auguste_Dominique_Ingres.jpg "The Death of Leonardo da Vinci, by Ingres, 1818")

---

### **Tables**

---
Tables, _as we hope_, are easy to interpret and to create. Simply use horizontal
rules to separate cells. The header is always defined by the first line, while
the second line is used to separate the table header from the body visually and
to define the column alignment.

**Markdown-format:**

<!-- class="translate"-->
``` markdown
| Tables               |      Are      |  Cool |
| -------------------- |:-------------:| -----:|
| *** columns 3 is *** | right-aligned | $1600 |
| ** column 2 is **    |   centered    |   $12 |
| * zebra stripes *    |   are neat    |    $1 |
```

As you can see in the result, you can sort tables, by clicking onto the icon
that appears on the right of every header cell. A table will then be either
sorted ascending, descending, or not sorted, which means your initial row order
will be restored.

**Result:**

| Tables               |      Are      |  Cool |
| -------------------- |:-------------:| -----:|
| *** columns 3 is *** | right-aligned | $1600 |
| ** column 2 is **    |   centered    |   $12 |
| * zebra stripes *    |   are neat    |    $1 |

The position of the colon defines whether a column should be centered, aligned
to the left or to the right. By default, if you do not use colons, all columns
are aligned to the left.

* centered --> `:---:`
* right --> `---:`
* left --> `:---` or `---` (default)

---

### **Code**

---

In Markdown, you can use a sequence of at least three subsequent backticks `\``
to indicate a code-block that should not be treated as Markdown, but instead
contains some kind of code for which syntax-highlighting should be used, if
possible. The first word after the backticks is used as an indicator, for which
kind of syntax-highlighting should be applied.

**syntax for code:**

```` markdown
```python

```
````

````md
```python
import time
# Quick, count to ten!
for i in range(10):
    # (but not *too* quick)
    time.sleep(0.5)
    print(i)
```
````

In case you are wondering, how to embed a code-block into a code-block with
backticks? Three backticks are the minimum, thus you can surround your Markdown
code-block example with a sequence of 4 or more backticks. If you start with
four backticks, LiaScript will parse everything as code until it reaches a
matching number of backticks.


```python
import time
# Quick, count to ten!
for i in range(10):
  # (but not *too* quick)
  time.sleep(0.5)
  print(i)
```

---

### **Blockquotes**

**Markdown-Syntax:**

<!-- class="translate"-->
``` md
> This was said some time ago ...
>
>> This was said even longer ago,
> > I guess ...
>
> * aleph
> * beth
```

As you can see from the example, all Markdown elements can be used within a
blockquote and vice versa. Everything you have learned so far can be easily
combined, it could also be a gallery or an embedded object...

**Result:**

> This was said some time ago ...
>
>> This was said even longer ago,
> > I guess ...
>
> * aleph
> * beth

### Horizontal rules

**Markdown-Syntax:**

``` markdown
some paragraph

---

something else

----------------
```

**Result:**

some paragraph

---

something else

----------------

