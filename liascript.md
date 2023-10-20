<!--

author:   Padmanabhan S
email:    g.s.r.padmanabhan@gmail.com
version:  0.0.1
language: en
narrator: UK English Male

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://felixhao28.github.io/JSCPP/dist/JSCPP.es5.min.js

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css

link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css



-->

# Liascript documentation

In this document you will find to use a liascript features and how to create a liascript document using markdown.

## **Table of contents**

* [**Introduction**](#introduction)
* [**Editors**](#editors)
* [**Markdown Syntax**](#markdown-syntax)
* [**Animations**](#animations)
* [**Interactive Code**](#interactive-code)
* [**Conclusions**](#conclusions)
* [**References**](#references)

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
* [**Horizontal rules**](#horizontal-rules)
* [**Lia-keep**](#lia-keep)

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

### **Horizontal rules**

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

### **Lia-keep**

If you want to embed more complex HTML, and only HTML, without taking care about
indentation and formatting, then should use the `lia-keep` tag to surround your
code.

```html
<lia-keep>
  <style>
    table, th, td {
      border: 1px solid black;
      width: 250px; height: 40px;
      text-align: center;
    }
  </style>

  <table style="margin: 1em">
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
    <tr>
      <td>Cell 1</td>
      <td rowspan="2">Cell 2</td>
    </tr>
    <tr>
      <td>Cell 3</td>
    </tr>
  </table>
</lia-keep>


<lia-keep>

      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg/764px-Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg" width="200" height="200" alt="The Virgin and Child with Saint Anne, c. 1501–1519, Louvre, Paris">

</lia-keep>
```

As it is demonstrated in the result, everything within this tag will be treated as HTML only, no Markdown parsing will be applied and indentation will be checked.

**Result:**

<lia-keep>
  <style>
    table, th, td {
      border: 1px solid black;
      width: 250px; height: 40px;
      text-align: center;
    }
  </style>

  <table style="margin: 1em">
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
    <tr>
      <td>Cell 1</td>
      <td rowspan="2">Cell 2</td>
    </tr>
    <tr>
      <td>Cell 3</td>
    </tr>
  </table>
</lia-keep>

<lia-keep>

      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg/764px-Leonardo_da_Vinci_-_Virgin_and_Child_with_St_Anne_C2RMF_retouched.jpg" width="200" height="200" alt="The Virgin and Child with Saint Anne, c. 1501–1519, Louvre, Paris">

</lia-keep>

This way, you could for example also import even more complex HTML-tables, pictures with multiple sources for different screen-sizes, and more. With great power comes great responsibility. Thus, you will also be responsibile for your styling.

## **Animations**

Animations are defined by two curly braces and one starting and one optional ending number. Animations can be associated to single blocks, multiple blocks and also inlined.

* [**Block-Animations**](#block-animations)
* [**Multi-Block Animations**](#multi-block-animations)
* [**Inline-Animations**](#inline-animations)
* [**Combinations & Styling Animations**](#combinations-&-styling-animations)
* [**Comments: Text 2 Speech**](#comments:-text-2-speech)

### **Block-Animations**

Animations can be associated to blocks, simply by adding two curly braces on top of a block.
We recommend applying indentation of at least spaces to an animations definitions.
Other Markdown renderer will highlight this as code, such that it is easier to read.

``` markdown
     {{1}}
This is an example for a *single* block animations.

     {{2-3}}
This one will appear on animation step 2 and disappear on 3.

{{4}} This is also ok, but it will look be harder to spot on GitHub.
```

Use a starting and an ending number, if you want the element to disappear at a certain point.

**Result:**

     {{1}}
This is an example for a *single* block animations.

     {{2-3}}
This one will appear on animation step 2 and disappear on 3.


{{4}} This is also ok, but it will look be harder to spot on GitHub.

### **Multi-Block Animations**

* You can group multiple markdown blocks by lines of asterisks.
* Simply add the curly braces with the animation definition above the upper line.

``` markdown
            {{1-2}}
************************************

This is an example...

| that     | contains |
|----------|----------|
| multiple | blocks.  |

************************************


             {{2}}
<section>

As an alternative, you can also use
HTML-tags ...


... to surround multiple blocks.

</section>
```

* Blocks can also have a starting and disappearing number.
* Depending on your preferred style, you can also use HTML-tags to group blocks.
* These will then be displayed slightly different on [GitHub](https://github.com).

__Result:__

            {{1-2}}
************************************

This is an example...

| that     | contains |
|----------|----------|
| multiple | blocks.  |

************************************


             {{2}}
<section>

As an alternative, you can also use
HTML-tags ...


... to surround multiple blocks.

</section>

### **Inline-Animations**

Animations can also be associated to inline elements, simply by adding two curly braces around the element.

``` markdown
* no effect here
* but in this line {2}{show ***second***}
* as well as this one {1-2}{show ***first*** remove on __second__}
```

**Result:**

* no effect here
* but in this line {2}{show ***second***}
* as well as this one {1-2}{show ***first*** remove on __second__}

### **Combinations & Styling Animations**

Animations can also be grouped freely, such that one multi-block animation can contain multiple block animations and one block can also contain further inline animations:

``` markdown
<!--
class="animate__animated animate__backInUp"
style="background:#CCC; padding:3rem; min-height: 40vh; border-radius: 3rem"
-->
                 {{1}}
*******************************************

This block contains {2}{multiple} inline animations.
With some
{2-3}{styled}<!-- class="animate__animated animate__flash" -->
elements as well.

<!-- class="animate__animated animate__backInDown" -->
                  {{3}}
!?[Animated paintings](https://www.youtube.com/watch?v=-DDphfCnFQc&autoplay=true)

*******************************************
```

<!--
class="animate__animated animate__backInUp"
style="background:#CCC; padding:3rem; min-height: 40vh; border-radius: 3rem"
-->
                 {{1}}
*******************************************

This block contains {2}{multiple} inline animations.
With some
{2-3}{styled}<!-- class="animate__animated animate__flash" -->
elements as well.

<!-- class="animate__animated animate__backInDown" -->
                  {{3}}
!?[Animated paintings](https://www.youtube.com/watch?v=-DDphfCnFQc&autoplay=true)

*******************************************

### **Comments: Text 2 Speech**

The idea of a comment is that they should be associated to witch animations.
When animation $x$ is revealed, then the comment $x$ is read aloud. 
Like in a PowerPoint presentations, when one element appears and the presenter says something, clicks the next element appears and is also commented.
Thus, a comment is a paragraph that is marked by two curly braces, which contain a number, and two dashes around the braces.
If multiple comments have the same number, then they will be replayed in the order of appearance.

``` markdown
          --{{1}}--
This will be spoken out loud.

          --{{2}}--
This will be spoken out loud too,
but at animation step 2.

          --{{2}}--
Don't forget me.

       {{1}}
__I am animation 1 {2}{and 2 too}.__
```

          --{{1}}--
This will be spoken out loud.

          --{{2}}--
This will be spoken out loud too,
but at animation step 2.

          --{{2}}--
Don' forget me.

       {{1}}
__I am animation 1 {2}{and 2 too}.__

## **Interactive Code**

In section [Code](#code) we had already introduced how code-snippets can be defined in Markdown and LiaScript.
In this part we will introduce how such code can be made executable and editable.

* [**Starting simple**](#starting-simple)
* [**Projects**](#projects)
* [**Loading external Resources**](#loading-external-resources)
* [**Examples**](#examples)

### **Starting simple**

Any code snippet can be made interactive by attaching a script-tag to the end.
The `@input` is simply a placeholder that gets replaced by the current user-input.

```` markdown
``` javascript
var i=0;
var j=0;
var result = 0;

for(i = 0; i<10; i++) {
    for(j = 0; j<i; j++) {
        result += j;
        console.log("(", i, ",", j, ") result", result)
    }
}
// the last statement defines the return statement
result;
```
<script>@input</script>
````

If the code is in JavaScript and provides a full and executable example, not only pseudo-code, then it can be directly executed.
Just click on the run-button directly below the editor.
The console output will be piped into the local shell that appears below the code-snippet.

``` javascript
var i=0;
var j=0;
var result = 0;

for(i = 0; i<10; i++) {
    for(j = 0; j<i; j++) {
        result += j;
        console.log("(", i, ",", j, ") result", result)
    }
}
// the last statement defines the return statement
result;
```
<script>@input</script>

### **Projects**

Multiple different code snippets can be combined to form a larger projects too.
It requires to write them in a row.
You can give them names, if you add a second parameter after the highlighting definition.
Add a `+` or `-` to the front of your filename, in order to indicate, if it should be visible by default or not.

```` markdown
``` js     +EvalScript.js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```
``` json    +Data.json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```
<script>
  // insert the JSON dataset into the local variable data
  let data = @input(1);

  // eval the script that uses this dataset, but just
  // inserting the @input, which already contains JS code
  // would be also fine ... 
  eval(`@input(0)`);
</script>
````

The result is a project which consists of two files.
Each file can be edited separately, while the script tag provides only some basic glue-code that tells LiaScript what to do with the input.

``` js     +EvalScript.js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```
``` json    +Data.json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```
<script>
  // insert the JSON dataset into the local variable data
  let data = @input(1);

  // eval the script that uses this dataset
  @input
</script>

### **Loading external Resources**

If you want to make use of some external functionality, you can also load additional JavaScript modules into LiaScript.
Simply add the `script` command to the main definition of your LiaScript header.

``` markdown
<!--
author: ...

script: https://cdn.rawgit.com/davidedc/Algebrite/master/dist/algebrite.bundle-for-browser.js
-->

# Title

...
```

If this library has been loaded, it can be used also directly within the script-tag.
In this case we made use of the Computer-Algebra-System ([Algebrit](http://algebrite.org)), which is used to solve some algebraic equations.

```` markdown
```javascript
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
<script> Algebrite.run(`@input`) </script>
````

The result is a fully functional computer algebra editor where you can experiment and modify equations.


```javascript
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
<script> Algebrite.run(`@input`) </script>

### **Examples**

* [**JavaScript Chartlist**](#javascript-chartlist)
* [**Computer-Algebra**](#computer-algebra)
* [**C++**](#c++)

#### **JavaScript Chartlist**

A drawing example, for demonstrating that any javascript library can be used,
also for drawing.

```` javascript
<link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">

``` javascript
// Initialize a Line chart in the container with the ID chart1
new Chartist.Line('#chart1', {
  labels: [1, 2, 3, 4],
  series: [[100, 120, 180, 200]]
});

// Initialize a Line chart in the container with the ID chart2
new Chartist.Bar('#chart2', {
  labels: [1, 2, 3, 4],
  series: [[5, 2, 8, 3]]
});
```
<script>@input</script>

<div class="ct-chart ct-golden-section" id="chart1"></div>
<div class="ct-chart ct-golden-section" id="chart2"></div>
````

<link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">

``` javascript
// Initialize a Line chart in the container with the ID chart1
new Chartist.Line('#chart1', {
  labels: [1, 2, 3, 4],
  series: [[100, 120, 180, 200]]
});

// Initialize a Line chart in the container with the ID chart2
new Chartist.Bar('#chart2', {
  labels: [1, 2, 3, 4],
  series: [[5, 2, 8, 3]]
});
```
<script>@input</script>

<div class="ct-chart ct-golden-section" id="chart1"></div>
<div class="ct-chart ct-golden-section" id="chart2"></div>

#### **Computer Algebra**
<!--
script:   https://cdn.rawgit.com/davidedc/Algebrite/master/dist/algebrite.bundle-for-browser.js
-->

An example of a Computer-Algebra-System (Algebrit), see http://algebrite.org for more examples:

```` javascript
``` javascript
x + x
```
<script> Algebrite.run(`@input`) </script>



```javascript
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
<script> Algebrite.run(`@input`) </script>
````

``` javascript
x + x
```
<script> Algebrite.run(`@input`) </script>



```javascript
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
<script> Algebrite.run(`@input`) </script>

#### **C++**

Teaching other language-basics is also possible, for this example we applied [JSCPP](https://github.com/felixhao28/JSCPP)
to run simple C++ programs:

```` markdown
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 120;
    int rslt = 0;
    for(int i=1; i<a; ++i) {
        rslt += i;
        cout << "rslt: " << rslt << endl;
    }
    cout << "final result = " << rslt << endl;
    return 0;
}
```
<script>
  var output = "";
  JSCPP.run(`@input`, "", {stdio: {write: s => { output += s }}});
  output;
</script>
````

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 120;
    int rslt = 0;
    for(int i=1; i<a; ++i) {
        rslt += i;
        cout << "rslt: " << rslt << endl;
    }
    cout << "final result = " << rslt << endl;
    return 0;
}
```
<script>
  var output = "";
  JSCPP.run(`@input`, "", {stdio: {write: s => { output += s }}});
  output;
</script>

## **Conclusion**

LiaScript is a new way of creating interactive online courses. It is easy to learn and to use, and it is compatible with Markdown. This means, if you are already familiar with Markdown, you can easily start using LiaScript. The additional features of LiaScript are introduced step-by-step, such that you can also use it for your daily work. LiaScript is not only a new way of creating
online courses, it is also a new way of creating interactive books, tutorials, and much more. It is a new way of sharing knowledge!

## **References**

* [**LiaScript**](https://LiaScript.github.io) - The official LiaScript website
* [preview-lia](https://raw.githubusercontent.com/LiaScript/docs/master/README.md)

--{{0}}--
`[preview-lia](https://raw.githubusercontent.com/LiaScript/docs/master/README.md)`