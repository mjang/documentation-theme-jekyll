---
title: Samples Page
category: Samples
category-order: 1000
order: 1
excluded_in_navigation: true
excluded_in_search: true
---

I am a paragraph - the ForgeRock Identity Cloud is a cloud-based identity and access management service that allows developers to quickly integrate authentication and identity management into their applications.

I am another paragraph - by using ForgeRock cloud for authentication you can just get on with making a great app for your business. We'll take care of securing signup, login and related identity meta data.


# H1
## H2
### H3
#### H4
##### H5
###### H6

<br />

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~


1. First ordered list item
2. Another item
-  Unordered sub-list. 
1. more
4. more it doesn't matter that this number is wrong in the code, just that it's a number.

* Unordered list can use asterisks
- Or minuses
+ Or pluses

[I am a link](http://github.com)

I am an internal link [the latest changes]({{ site.baseurl }}/changelog/)


**Here is a horizontal rule** 

Three or more...

---


#### Here's an example of adding an image

![](//placehold.it/800x300)

![]({{ site.baseurl }}/images/404.png)



#### Here are some buttons with icons

<form action="{{ site.baseurl }}/signup/" method="get">

  <button type="button" class="btn btn-primary"><i class="material-icons">file_download</i> primary</button>

  <button type="button" class="btn btn-secondary"><i class="material-icons">adb</i> secondary</button>

  <button type="button" class="btn btn-accent"><i class="material-icons">fingerprint</i> accent</button>

  <button type="button" class="btn btn-transparent"><i class="material-icons">visibility_off</i> transparent</button>

</form>

### Here's a quick tip call out

> Have questions or feedback? Send us a message at [questions@forgerock.com](mailto:questions@forgerock.com)


### Here's a block quote

> **Sample App** <br>
Download the sample app below or branch from github.<br><br>
<button type="button" class="btn btn-secondary"><i class="material-icons">file_download</i> DOWNLOAD</button>&nbsp;&nbsp;&nbsp;{% octicon mark-github class:"right left" aria-label:hi %}&nbsp;&nbsp;[View on Github](http://github.com){: .important}
{: .plain-blockquote}

---


#### Here's some example code formatted as javascript...


```javascript
app.get('/', (req,res) =>{
  console.log(req.rawHeaders)
  res.render('home.hbs',{
    pageTitle:'Home page'
  })
})
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```

### Tables
- Text in tables should be left aligned
- Numbers should be right aligned

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3







