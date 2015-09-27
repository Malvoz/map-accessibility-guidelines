# Alternative Text

Alternative text provides a textual alternative to non-text content in web pages (i.e. static maps, and/or images). Alternative text is especially helpful for people who are blind and rely on a screen reader to have the content of the website read to them.

When using alternative text, describe the **_content and function_** providing a semantic meaning and description of the images, which is also used by search engines. For example, if you have an image thumbnail of a regional park map you could label the image alternative text to reflect the content of the image:
```html
<!-- An example of an alternative text tag -->
<alt="Regional park map">
```

However, not all images are as clear cut. For example, if you have an image of a girl that is being used as context of human health an alternative text of `<alt="girl">` isn't helpful for those with screen readers. In fact, there is no right answer in this case as it is difficult to provide content and/or function to a screen reader so in the case an empty alt tag may be the best option:
```html
<!-- Sometimes an empty alternative text tag is the answer -->
<alt="">
```

A good example within your content could be:
```html
<!-- A full example of the alternative text tag -->
<img src="/images/park_map.png" alt="Regional park map" width="400" height="800" border="0">
```