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


``` markdown
\*, \~, \_, \#, \{, \}, \[, \], \|, \`, \$, \@, \\, \<, \>
```

**Result:** \*, \~, \_, \#, \{, \}, \[, \], \|, \`, \$, \@, \\, \<, \>

### **Lists**

---

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

---

### **Tables**

---


---

### **Code**

---

---

### **Math**

---

---

### **Macros**

---

---

### **Comments**

---

---