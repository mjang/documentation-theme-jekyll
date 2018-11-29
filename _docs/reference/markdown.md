---
title: Markdown Cheat Sheet 
category: Reference
category-order: 5
order: 2
excluded_in_navigation: true
excluded_in_search: true
---

You can use markdown in the email templates to format your emails, add images, headers, css and more.


##### Table of Contents  
- [Headers](#headers)  
- [Emphasis](#emphasis)  
- [Typographic Replacements](#typographic)  
- [Lists](#lists)  
- [Links](#links)  
- [Styles](#styles)  
- [Images](#images)  
- [Tables](#tables)  
- [Blockquotes](#blockquotes)  
- [Inline HTML](#html)  
- [Horizontal Rule](#hr)  
- [Line Breaks](#lines)  
- [Footnotes](#footnotes)  


---


<a name="headers"/>

## Headers

```no-highlight
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

# H1
## H2
### H3
#### H4
##### H5
###### H6

---

<a name="emphasis"/>

## Emphasis

```no-highlight
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

---

<a name="typographic"/>

## Typographic Replacements


```no-highlight
(c) (C) (r) (R) (tm) (TM) (p) (P) +-
```

© © ® ® ™ ™ § § ±

---

<a name="lists"/>

## Lists

```
Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar
```


#### Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

#### Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`


---

<a name="links"/>

## Links

```no-highlight
[link text](http://forgerock.com)

[link with title](http://forgerock.com "title text!")

Autoconverted link http://forgerock.com
```

[link text](http://forgerock.com)

[link with title](http://forgerock.com "title text!")

Autoconverted link [http://forgerock.com](http://forgerock.com)

---

<a name="styles"/>

## Styles

```no-highlight
# header {.style-me}
paragraph {data-toggle=modal}

output

<h1 class="style-me">header</h1>
<p data-toggle="modal">paragraph</p>

```


---

<a name="images"/>

## Images

```no-highlight
Inline-style: 
![alt text](https://www.forgerock.com/resources/view/64329345/logo/1Cblacksquare.png "ForgeRock Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://www.forgerock.com/resources/view/64329345/logo/1Cblacksquare.png "ForgeRock Logo Title Text 2"
```



Hover over the logo to see the title text

Inline-style: 
![alt text](https://www.forgerock.com/resources/view/64329345/logo/1Cblacksquare.png "ForgeRock Logo Title Text 1"){:width="48px"}

Reference-style: 
![alt text][logo]

[logo]: https://www.forgerock.com/resources/view/64329345/logo/1Cblacksquare.png "ForgeRock Logo Title Text 2"
{:width="48px"}



---


<a name="tables"/>

## Tables

Tables aren't part of the core Markdown spec, but they are part of GFM and *Markdown Here* supports them. They are an easy way of adding tables to your email -- a task that would otherwise require copy-pasting from another application.

```no-highlight
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
```


| Tables        | Are           | Cool |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3


---


<a name="blockquotes"/>

## Blockquotes

```no-highlight
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 
```

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 



---


<a name="html"/>

## Inline HTML

```no-highlight
<dl>
  <dt>Definition list</dt>
  <dd>Is something you can use.</dd>
  <dt>Definition list</dt>
  <dd>Is something you can use.</dd>
</dl>
```

<dl>
  <dt>Definition list</dt>
  <dd>Is something you can use.</dd>
    <dt>Definition list</dt>
  <dd>Is something you can use.</dd>
</dl>


---

<a name="hr"/>

## Horizontal Rule

```
Three or more...

---

Hyphens

***

Asterisks

___

Underscores
```


---

<a name="lines"/>

## Line Breaks

When you hit 'enter' a new paragraph will be created.

```
Here's some text.

Some more text, but now I am a new paragraph because someone hit 'enter' above me.
```

---

<a name="footnotes"/>

## Footnotes

They can't be added directly but you can add an image with a link to the video like this:

```no-highlight
Footnote 1 link[^first].

Footnote 2 link[^second].
```


Footnote 1 link[^first].

Footnote 2 link[^second].

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.

---
