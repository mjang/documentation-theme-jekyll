---
title: Javascript
category: Sample Apps
category-order: 2
order: 2
---

Vestibulum gravida sollicitudin neque, a porta massa congue eget. Quisque ultrices arcu elit, eu viverra arcu molestie quis. Morbi dignissim et magna nec bibendum. Duis blandit arcu a leo mattis, congue sagittis mauris mattis. Donec vel finibus urna. Nullam a mollis quam, sed hendrerit nulla. In volutpat diam diam, ut iaculis risus consectetur ac. Cras ac ex ligula. Fusce volutpat tempor mauris in imperdiet. Ut tincidunt justo vel enim aliquet semper


```
app.get('/', (req,res) =>{
  console.log(req.rawHeaders)
  res.render('home.hbs',{
    pageTitle:'Home page'
  })
})
```
{: .language-javascript}
